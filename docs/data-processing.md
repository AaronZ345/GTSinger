[Back to GTSinger](../README.md)

# Data processing

The code for processing the dataset is provided in the [`Data-Process`](../Data-Process).

## Environment (run from the repository root)

A suitable [conda](https://docs.conda.io/en/latest/) environment named `gt_dataprocess` can be created and activated with:

```bash
conda create -n gt_dataprocess python=3.8 -y
conda activate gt_dataprocess
python -m pip install -r Data-Process/requirements.txt
```

## Validation scripts

The code for checking the dataset is provided in `../Data-Process/check/`, including the following files:

- `check_file_and_folder.py`: Check the file and folder structure of the dataset.

- `check_valid_bandwidth.py`: Check the sample rate and valid bandwidth of the dataset.

- `count_time.py`: Count the time of the singing voice and speech in the dataset.

- `plot_f0.py`: Plot the pitch(f0) of the singing voice audio.

- `plot_mel.py`: Plot the mel-spectrogram of audio.

## Annotation and segmentation scripts

The code for preprocessing the dataset is provided in `../Data-Process/process/`, including the following files:

- `gen_final_json.py`: Generate the final JSON file for each singing voice based on the TextGrid file and musicxml file that have been annotated.

- `global2tgjson.py`: Add global style labels to the JSON file and TextGrid file.

- `seg_singing.py` & `seg_speech.py`: Segment the singing voice and speech based on the TextGrid file.
