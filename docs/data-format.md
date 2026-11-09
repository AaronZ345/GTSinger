[Back to GTSinger](../README.md)

# Data format

Our dataset is organized hierarchically. 

It presents nine top-level folders, each corresponding to a distinct language. 

Each language contains singer folders. Each singer folder has five technique categories; mixed voice and falsetto share one category.

These technique folders contain numerous song entries, with each song further divided into several controlled comparison groups: a control group (natural singing without the specific technique), and a technique group (densely employing the specific technique).

Our singing voices and speech are recorded at a 48kHz sampling rate with 24-bit resolution in WAV format. 

Alignments and annotations are provided in TextGrid files, including word boundaries, phoneme boundaries, phoneme-level annotations for six techniques, and global style labels (singing method, emotion, pace, and range). 

We also provide realistic music scores in musicxml format.

Notably, we provide an additional JSON file for each singing voice, facilitating data parsing and processing for singing models.

Here is the data structure of our dataset:

```
.
├── Chinese
│   ├── ZH-Alto-1
│   └── ZH-Tenor-1
├── English
│   ├── EN-Alto-1
│   │   ├── Breathy
│   │   ├── Glissando
│   │   │   └── my love
│   │   │       ├── Control_Group
│   │   │       ├── Glissando_Group
│   │   │       └── Paired_Speech_Group
│   │   ├── Mixed_Voice_and_Falsetto
│   │   ├── Pharyngeal
│   │   └── Vibrato
│   ├── EN-Alto-2
│   │   ├── Breathy
│   │   ├── Glissando
│   │   ├── Mixed_Voice_and_Falsetto
│   │   ├── Pharyngeal
│   │   └── Vibrato
│   └── EN-Tenor-1
│       ├── Breathy
│       ├── Glissando
│       ├── Mixed_Voice_and_Falsetto
│       ├── Pharyngeal
│       └── Vibrato
├── French
│   ├── FR-Soprano-1
│   └── FR-Tenor-1
├── German
│   ├── DE-Soprano-1
│   └── DE-Tenor-1
├── Italian
│   ├── IT-Bass-1
│   ├── IT-Bass-2
│   └── IT-Soprano-1
├── Japanese
│   ├── JA-Soprano-1
│   └── JA-Tenor-1
├── Korean
│   ├── KO-Soprano-1
│   ├── KO-Soprano-2
│   └── KO-Tenor-1
├── Russian
│   └── RU-Alto-1
└── Spanish
    ├── ES-Bass-1
    └── ES-Soprano-1
```
