# ライセンス

**このリポジトリは 1 つのライセンスでは配れない。**素材ごとに条件が違うので、
ファイル単位で示す。画面右下の「ライセンスと注意事項」にも同じことが書いてある。

## ファイルごとの条件

| ファイル | 条件 |
|---|---|
| `brain_arterial.glb`, `assets/*/label_atlas_arterial.webp` | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)（JHU Arterial Atlas から継承） |
| `brain_tract.glb`, `tract_lut.txt` | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)（HCP1065 Tractography Atlas から継承）。下記 HCP の謝辞も必要 |
| `assets/*/t1_atlas.webp` | [WU-Minn HCP Open Access Data Use Terms](https://www.humanconnectome.org/study/hcp-young-adult/document/wu-minn-hcp-consortium-open-access-data-use-terms)（**同じ条件でのみ再配布可**） |
| `brain_glasser.glb`, `brain_network.glb`, `assets/*/label_atlas_glasser.webp`, `assets/*/label_atlas_network.webp` | 同上。区分の定義は HCP-MMP1、fsaverage への投影（Mills 2016）は [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) |
| `brain.glb`, `brain_macro.glb`, `assets/*/label_atlas.webp`, `assets/*/label_atlas_macro.webp` | 標準脳の由来として上記 HCP の条件。区分の推定は FastSurfer（Apache License 2.0）、定義は Klein &amp; Tourville 2012 |
| `vendor/three/` | MIT License（無改変で同梱） |
| `viewer.html`, `labels.json`, `index.html`, `docs/` | 著作権は作成者。上の素材を**表示するための独立した著作物**で、CC BY-SA の継承対象ではない（収集物であって翻案ではない） |

## Human Connectome Project の謝辞

HCP 由来の素材（標準脳の MRI・HCP-MMP1・HCP1065）を使うときは、次の文言を
入れることが条件になっている。

> Data were provided [in part] by the Human Connectome Project, WU-Minn Consortium
> (Principal Investigators: David Van Essen and Kamil Ugurbil; 1U54MH091657) funded by
> the 16 NIH Institutes and Centers that support the NIH Blueprint for Neuroscience
> Research; and by the McDonnell Center for Systems Neuroscience at Washington University.

## 出典

- Liu C-F, et al. *Digital 3D Brain MRI Arterial Territories Atlas.*
  Scientific Data 10, 74 (2023). © 2021 The Johns Hopkins University
- Glasser MF, et al. *A multi-modal parcellation of human cerebral cortex.*
  Nature 536, 171–178 (2016)
- Yeh F-C. *Population-based tract-to-region connectome of the human brain and its
  hierarchical topology.* Nature Communications 13, 4933 (2022)
- Klein A, Tourville J. *101 labeled brain images and a consistent human cortical
  labeling protocol.* Frontiers in Neuroscience 6, 171 (2012)

## 確認できていないこと

**標準脳 (`assets/*/t1_atlas.webp` の元になった画像) の配布元が記録されていない。**
ヘッダから分かるのは Connectome Workbench 1.5.0 が書き出した頭蓋剥離済みの MNI 空間の
画像だということだけで、どこから取得したかの記録が残っていない。Connectome Workbench は
HCP のツールなので HCP 由来とみて、**条件の厳しいほう**（HCP Open Access Data Use Terms）
に従うものとして扱っている。
