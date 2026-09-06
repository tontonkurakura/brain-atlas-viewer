# brain-atlas-viewer

3D の脳モデルを断面で切り、切り口に MRI と領域色を出す Web ビューア。5 つの
アトラスを切り替えて見る。

**[開く](https://tontonkurakura.github.io/brain-atlas-viewer/viewer.html)**

![機能的領域を冠状断で切ったところ](docs/screenshot.png)

## 中身

| アトラス | 区分 | 出どころ |
|---|---|---|
| 解剖学領域（マクロ） | 10 | DKT を脳葉などへまとめたもの。**既定** |
| 解剖学領域（ミクロ） | 93 | Desikan-Killiany-Tourville |
| 血管支配領域 | 32 | JHU Arterial Atlas Level 1 |
| 機能的領域 | 360 | HCP-MMP1（Glasser）。解剖 22 区分と Yeo 7 ネットワークで並べ替えられる |
| トラクトグラフィー | 87 | HCP1065 の平均トラクト（1065 例）。streamline をそのまま線で描く |

## 作り

- 標準脳は MNI152。3D モデルと断面画像を重ねて見せる
- **座標はすべて world RAS (mm)。**メッシュも断面もクリップ面も同じ数値なので、
  座標変換のコードが存在しない。詳しくは [docs/spec.md](docs/spec.md)
- 依存は同梱の three.js r163 だけ。ビルド手順も外部への通信も無い
- 静的ファイルを配るだけで動く

```bash
python3 -m http.server 8791    # このフォルダで
```

**`file://` では動かない。**ブラウザが `file://` からのデータ取得を遮断するため、
断面画像も 3D モデルも届かない。開くと画面がそう言う。

## 使うにあたって

**教育と参照を目的としている。診断・治療の判断には使わないこと。**表示している
のは標準脳に公開アトラスを当てはめた区分で、区分の境界にも血管や線維の走行にも
個人差がある。個々の症例の解剖と一致することを保証するものではない。左右の向きは
neurological（画像の左が患者の左）。

## ライセンスと出典

**1 つのライセンスでは配れない。**ファイルごとの条件は [LICENSE.md](LICENSE.md) に
まとめてある。要点だけ:

| | |
|---|---|
| `brain_arterial.glb` / `brain_tract.glb` とその断面画像 | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)（JHU Arterial Atlas と HCP1065 から継承） |
| 標準脳の MRI と HCP 系のアトラス | [WU-Minn HCP Open Access Data Use Terms](https://www.humanconnectome.org/study/hcp-young-adult/document/wu-minn-hcp-consortium-open-access-data-use-terms)（**同じ条件でのみ再配布可**。定型の謝辞も要る） |
| `vendor/three/` | MIT |

画面右下の「ライセンスと注意事項」にも同じことが書いてある。

## このリポジトリについて

生成物だけを置いてある。作っているのは別のリポジトリで、そちらに資産を作る
Python のパイプラインと、ビューアの元がある。

参照実装として別の開発者へ渡している版が
[brain-slice-viewer](https://github.com/tontonkurakura/brain-slice-viewer) にある。
あちらはアトラス 3 つで止めてあり、座標の取り決めと手法を伝えることが目的。
