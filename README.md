# RVC on Mac

For using the Retrieval-based-Voice-Conversion-WebUI on Mac. Temporary fix for the broken support.

[Original README](./README_original.md)

## Preparation

```bash
brew install python@3.10
brew install ffmpeg
brew install aria2
git clone https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI.git
cd Retrieval-based-Voice-Conversion-WebUI
```

Install the dependencies and download the models:

```bash
poetry lock
poetry install
. ./venv/bin/activate
./tools/dlmodels.sh
```

Start the web UI:

```bash
poetry run python infer-web.py --pycmd python
```

## Usage

### Training

In the web UI, select 'Train'.  

Change the experiment name.  

Change the training folder to the folder that contains the audio samples that you want to copy. (I use about 20 minutes of wav recordings of my voice.)  

Select "rmvpe" pitch extraction algorithm.  

Use "One-click training" to start training.

The mps gpu support is broken, expect long training time.

### Inference

In the web UI, select 'Model Inference'.

Choose the model you trained.

Enter the audio file path you want to convert.

Click "Convert".
