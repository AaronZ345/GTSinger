<h1>GTSinger: A Global Multi-Technique Singing Corpus with Realistic Music Scores for All Singing Tasks<br>
  <a href="https://neurips.cc/virtual/2024/poster/97428"><img src="assets/readme/link-neurips.svg" alt="NeurIPS 2024 Spotlight" /></a>
</h1>

<p>
  <strong><a href="https://aaronz345.github.io/">Yu&nbsp;Zhang</a></strong>, Changhao&nbsp;Pan, Wenxiang&nbsp;Guo, Ruiqi&nbsp;Li, Zhiyuan&nbsp;Zhu, Jialei&nbsp;Wang,
  Wenhao&nbsp;Xu, Jingyu&nbsp;Lu, Zhiqing&nbsp;Hong, Chuxin&nbsp;Wang, LiChao&nbsp;Zhang, Jinzheng&nbsp;He,
  Ziyue&nbsp;Jiang, Yuxin&nbsp;Chen, Chen&nbsp;Yang, Jiecheng&nbsp;Zhou, Xinyu&nbsp;Cheng, Zhou&nbsp;Zhao
&ensp;<img src="assets/readme/affiliation-zju.svg" align="absmiddle" alt="Zhejiang University" />
</p>

<p>
  <a href="https://arxiv.org/abs/2409.13832"><img src="assets/readme/link-paper.svg" alt="Paper" /></a>
  <a href="https://aaronz345.github.io/GTSingerDemo"><img src="assets/readme/link-demo.svg" alt="Demo Page" /></a>
  <a href="https://huggingface.co/datasets/AaronZ345/GTSinger"><img src="assets/readme/link-dataset.svg" alt="Dataset" /></a>
  <a href="https://www.vc-challenge.org/"><img src="assets/readme/link-svcc.svg" alt="SVCC 2025" /></a>
  <a href="https://mp.weixin.qq.com/s/B1Iqr-24l57f0MslzYEslA"><img src="assets/readme/press-synced.svg" alt="机器之心" /></a>
  <a href="https://mp.weixin.qq.com/s/6RLdUzJM5PItklKUTTNz2w"><img src="assets/readme/press-paperweekly.svg" alt="PaperWeekly" /></a>
  <a href="https://zhuanlan.zhihu.com/p/993933492"><img src="assets/readme/press-zhihu.svg" alt="知乎" /></a>
</p>

## ![](assets/readme/section-overview.svg) Overview

GTSinger brings together **80.59 hours of singing** and **16.16 hours of paired speech** from **20 singers across 9 languages**. The studio recordings include manual phoneme alignments, annotations for **6 singing techniques**, global style labels, and realistic music scores.

See the [data format](docs/data-format.md) and [preprocessing guide](docs/data-processing.md) to run the [benchmarks](#benchmarks). To cite GTSinger, use the [BibTeX entry](#citations).

## ![](assets/readme/section-history.svg) News

- **2026.09** · Refined annotations for all nine languages.
- **2025.02** · Released all processed data and refined annotations for seven languages.
- **2024.09** · Released the full dataset.
- **2024.09** · GTSinger was accepted to NeurIPS 2024 as a Spotlight.
- **2024.05** · Released the code.

## ![](assets/readme/section-dataset.svg) Dataset

The full corpus, processed subsets, and refined paired speech are available for download. Annotation refinement for all nine languages was completed in September 2026.

[![Dataset on Hugging Face](assets/readme/link-dataset.svg)](https://huggingface.co/datasets/AaronZ345/GTSinger) [![Google Drive](assets/readme/link-drive.svg)](https://drive.google.com/drive/folders/1xcdvCxNAEEfJElt7sEP-xT8dMKxn1_Lz?usp=drive_link)

Use of the corpus is subject to the [dataset license](dataset_license.md).

| Resource | Files |
| --- | --- |
| Full recordings and annotations | WAV audio, TextGrid alignments, per-recording JSON, and MusicXML scores |
| Processed subsets | `metadata.json`, `phone_set.json`, and `spker_set.json` |

### Corpus contents

Each song includes a technique recording, a control recording for comparison, and paired speech. The [data-format guide](docs/data-format.md) explains how the recordings, annotations, and scores are organized.

<p align="center">
  <img src="https://raw.githubusercontent.com/AaronZ345/GTSingerDemo/f38fb85deaa2650313a57d4e12d7e81f0bf6887c/assets/fig1-DuVB278S.png" width="100%" alt="GTSinger pairs singing and speech with aligned TextGrid annotations and MusicXML scores, organized by language, singer, technique, and song." />
  <br>
  <sub><a href="https://arxiv.org/html/2409.13832v8#S1.F1">Figure 1</a>. Recordings, alignments, and scores for each song.</sub>
</p>

- **Languages:** Chinese, English, Japanese, Korean, Russian, Spanish, French, German, and Italian.
- **Singing techniques:** Mixed voice, falsetto, breathy, pharyngeal, vibrato, and glissando. Mixed voice and falsetto share a technique directory.
- **Audio:** 48 kHz, 24-bit WAV. The singers span all four vocal ranges.

### Data collection

We aligned both singing and speech. For singing, we also annotated technique and style and prepared realistic music scores before checking and segmenting the data.

<p align="center">
  <img src="assets/readme/figure-2-data-collection.png" width="100%" alt="GTSinger data collection pipeline from singing and speech recording through alignment, technique and style annotation, score transcription, data checking, and segmentation." />
  <br>
  <sub><a href="https://arxiv.org/html/2409.13832v8#S3.F2">Figure 2</a>. The GTSinger data collection pipeline.</sub>
</p>

## ![](assets/readme/section-benchmarks.svg) Benchmarks

Choose a processed subset and update its audio paths for your machine. Each benchmark guide covers its own environment and configuration.

| Benchmark | Related models |
| --- | --- |
| [Technique-controllable singing voice synthesis](Technique-Controllable%20SVS/readme.md) | [TCSinger](https://github.com/AaronZ345/TCSinger) |
| [Technique recognition](Tech-Recognition/readme.md) | Included benchmark |
| [Style transfer](Style%20Transfer/readme.md) | [StyleSinger](https://github.com/AaronZ345/StyleSinger), [TCSinger](https://github.com/AaronZ345/TCSinger) |
| [Speech-to-singing conversion](STS%20Conversion/readme.md) | [AlignSTS](https://github.com/RickyL-2000/AlignSTS) |

For dataset validation or annotation processing, start with the [preprocessing guide](docs/data-processing.md).

## ![](assets/readme/section-preprocessing.svg) Preprocessing

From the repository root:

```bash
git clone https://github.com/AaronZ345/GTSinger.git
cd GTSinger
conda create -n gt_dataprocess python=3.8 -y
conda activate gt_dataprocess
python -m pip install -r Data-Process/requirements.txt
```

| Directory | Purpose |
| --- | --- |
| [Data-Process/check](Data-Process/check) | Validate file layout, bandwidth, duration, F0, and mel spectrograms |
| [Data-Process/process](Data-Process/process) | Convert annotations, add global labels, and segment singing or speech |
| [Data-Process/utils](Data-Process/utils) | Phoneme and alignment utilities |

See the [script guide](docs/data-processing.md) before running preprocessing on a new dataset.

## ![](assets/readme/section-citations.svg) Citations

If you find this code useful in your research, please cite our work:
```bib
@article{zhang2024gtsinger,
  title={Gtsinger: A global multi-technique singing corpus with realistic music scores for all singing tasks},
  author={Zhang, Yu and Pan, Changhao and Guo, Wenxiang and Li, Ruiqi and Zhu, Zhiyuan and Wang, Jialei and Xu, Wenhao and Lu, Jingyu and Hong, Zhiqing and Wang, Chuxin and others},
  journal={arXiv preprint arXiv:2409.13832},
  year={2024}
}
```

## ![](assets/readme/section-disclaimer.svg) Disclaimer

Any organization or individual is prohibited from using any technology mentioned in this paper to generate someone's singing without his/her consent, including but not limited to government leaders, political figures, and celebrities. If you do not comply with this item, you could be in violation of copyright laws.
