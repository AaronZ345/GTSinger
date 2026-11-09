<div align="center">

# GTSinger

**A global multi-technique singing corpus with realistic music scores**

[NeurIPS 2024 Spotlight](https://neurips.cc/virtual/2024/poster/97428)

[![Paper](https://img.shields.io/badge/Paper-arXiv-b31b1b?style=flat-square)](https://arxiv.org/abs/2409.13832) [![Dataset](https://img.shields.io/badge/Dataset-Hugging%20Face-ffd21e?style=flat-square)](https://huggingface.co/datasets/AaronZ345/GTSinger) [![Demo](https://img.shields.io/badge/Demo-Samples-2563eb?style=flat-square)](https://aaronz345.github.io/GTSingerDemo) [![Stars](https://img.shields.io/github/stars/AaronZ345/GTSinger?style=flat-square)](https://github.com/AaronZ345/GTSinger)

[Download](#dataset) · [Data format](docs/data-format.md) · [Preprocessing](docs/data-processing.md) · [Benchmarks](#benchmarks) · [Citation](#citations)

</div>

| Singing | Paired speech | Singers | Languages | Singing techniques |
| :---: | :---: | :---: | :---: | :---: |
| 80.59 hours | 16.16 hours | 20 | 9 | 6 |

GTSinger contains studio-recorded singing, paired speech, manual phoneme alignments, technique annotations, global style labels, and realistic music scores. The repository provides data-processing tools and implementations of four benchmark tasks.

<p align="center">
  <img src="https://raw.githubusercontent.com/AaronZ345/GTSingerDemo/f38fb85deaa2650313a57d4e12d7e81f0bf6887c/assets/fig1-DuVB278S.png" width="100%" alt="GTSinger pairs singing and speech with aligned TextGrid annotations and MusicXML scores, organized by language, singer, technique, and song." />
</p>

## Dataset

**The full dataset and processed subsets are available. Annotations for all nine languages were refined by September 2026.**

| Resource | Contents | Access |
| --- | --- | --- |
| Full recordings and annotations | WAV audio, TextGrid alignments, per-recording JSON, and MusicXML scores | [Hugging Face](https://huggingface.co/datasets/AaronZ345/GTSinger) |
| Processed subsets | `metadata.json`, `phone_set.json`, and `spker_set.json` | [Hugging Face](https://huggingface.co/datasets/AaronZ345/GTSinger) |
| Download mirror | Dataset files | [Google Drive](https://drive.google.com/drive/folders/1xcdvCxNAEEfJElt7sEP-xT8dMKxn1_Lz?usp=drive_link) |
| Terms of use | Dataset license | [Read the license](dataset_license.md) |

Using GTSinger means accepting the [dataset license](dataset_license.md).

The languages are Chinese, English, Japanese, Korean, Russian, Spanish, French, German, and Italian. The six annotated techniques are mixed voice, falsetto, breathy, pharyngeal, vibrato, and glissando. Mixed voice and falsetto share one technique-folder category. Recordings cover all four vocal ranges and use 48 kHz, 24-bit WAV audio.

Choose the processed subset for your task, update its audio paths for your machine, and follow the corresponding benchmark guide below. The [data-format guide](docs/data-format.md) explains the control/technique groups, paired speech, annotations, and directory layout.

## Benchmarks

| Task | Implementation | Related models |
| --- | --- | --- |
| Technique-controllable singing voice synthesis | [Guide](Technique-Controllable%20SVS/readme.md) | [TCSinger](https://github.com/AaronZ345/TCSinger) |
| Technique recognition | [Guide](Tech-Recognition/readme.md) | Included benchmark |
| Style transfer | [Guide](Style%20Transfer/readme.md) | [StyleSinger](https://github.com/AaronZ345/StyleSinger), [TCSinger](https://github.com/AaronZ345/TCSinger) |
| Speech-to-singing conversion | [Guide](STS%20Conversion/readme.md) | [AlignSTS](https://github.com/RickyL-2000/AlignSTS) |

Each benchmark has its own environment and configuration. For dataset validation or annotation processing, start with the [preprocessing guide](docs/data-processing.md).

## Preprocessing

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

<details>
<summary>Release history and community links</summary>

- September 2026: completed annotation refinement for all nine languages.
- February 2025: released all processed data and refined seven languages.
- September 2024: released the full dataset; accepted to NeurIPS 2024 as a Spotlight.
- May 2024: released the code.

The code, full dataset, processed data, and paired-speech refinement are released. See [SVCC 2025](https://www.vc-challenge.org/), [机器之心](https://mp.weixin.qq.com/s/B1Iqr-24l57f0MslzYEslA), [PaperWeekly](https://mp.weixin.qq.com/s/6RLdUzJM5PItklKUTTNz2w), and [知乎](https://zhuanlan.zhihu.com/p/993933492).

</details>

<details>
<summary>Authors and affiliation</summary>

Yu Zhang*, Changhao Pan*, Wenxiang Guo*, Ruiqi Li, Zhiyuan Zhu, Jialei Wang, Wenhao Xu, Jingyu Lu, Zhiqing Hong, Chuxin Wang, LiChao Zhang, Jinzheng He, Ziyue Jiang, Yuxin Chen, Chen Yang, Jiecheng Zhou, Xinyu Cheng, Zhou Zhao | Zhejiang University

</details>

## Citations ##

If you find this code useful in your research, please cite our work:
```bib
@article{zhang2024gtsinger,
  title={Gtsinger: A global multi-technique singing corpus with realistic music scores for all singing tasks},
  author={Zhang, Yu and Pan, Changhao and Guo, Wenxiang and Li, Ruiqi and Zhu, Zhiyuan and Wang, Jialei and Xu, Wenhao and Lu, Jingyu and Hong, Zhiqing and Wang, Chuxin and others},
  journal={arXiv preprint arXiv:2409.13832},
  year={2024}
}
```

## Disclaimer ##

Any organization or individual is prohibited from using any technology mentioned in this paper to generate someone's singing without his/her consent, including but not limited to government leaders, political figures, and celebrities. If you do not comply with this item, you could be in violation of copyright laws.
