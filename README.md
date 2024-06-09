# WaveLip

WaveLip - a fully autonomous deepfake creator on your computer! It combines the [Wav2Lip](https://github.com/Rudrabha/Wav2Lip) and [Tortoise](https://github.com/neonbjb/tortoise-tts/tree/main) models, along with additional scripts for scraping video and audio from YouTube, so you can create a deepfake of any person you are interested in!

## Table of Contents

- [Installation](#installation)
  - [Wav2Lip Environment](#wav2lip-environment)
  - [Tortoise Environment](#tortoise-environment)
- [Usage](#usage)
- [Features](#features)
- [License](#license)
- [Contact](#contact)

## Installation

To install WaveLip, follow these steps:

1. Download the fully prepared project:
[Full Project](https://drive.google.com/file/d/1cdCYiqY-9IYiFrFOTtWYMBBIbrltALYc/view?usp=drive_link)

2. For each model, you will need a separate environment, otherwise, there will be a lot of dependency conflicts and you won't be able to run the application.

### Wav2Lip Environment:
```
conda create --name Wav2Lip python=3.11.9
conda activate Wav2Lip
pip install numpy
pip install librosa
pip install opencv-python
pip install tqdm
pip install batch_face
pip install ffmpeg-python
pip install pyaudio
pip install yt-dlp
pip install torch==2.3.0+cu118 torchvision==0.18.0+cu118 torchaudio==2.3.0 -f https://download.pytorch.org/whl/torch_stable.html
```
After installing all the packages, download [FFmpeg](https://ffmpeg.org/download.html)) and [yt-dlp](https://github.com/yt-dlp/yt-dlp)) and make sure they are added to your system's PATH environment variable.

### Tortoise Environment:
```
conda create --name Tortoise python=3.9 numba inflect
conda activate Tortoise
```
Install pytorch with the command provided here: [https://pytorch.org/get-started/locally/](https://pytorch.org/get-started/locally/)
Example:
```
conda install pytorch torchvision torchaudio pytorch-cuda=11.7 -c pytorch -c nvidia
```
Some dependencies:
```
pip install rotary-embedding-torch progressbar einops scipy unidecode transformers==4.31.0
```
If you have downloaded my fully prepared project, you don't need this command. If not, execute it as well:
```
git clone https://github.com/neonbjb/tortoise-tts.git
```
And run the setup.py file:
```
python setup.py install
pip install librosa==0.10.2.post1 audioread>=2.1.9 decorator>=4.3.0 lazy-loader>=0.1 msgpack>=1.0 pooch>=1.1 scikit-learn>=0.20.0 soxr>=0.3.2
```



## Usage

To create a full-fledged deepfake, you need to:

1. Use Tortoise to obtain an audio file voicing your text for the deepfake video. To use your voice for text voicing, simply add the folder with voice audio files to the `tortoise-voices` directory.

   Instructions for text voicing:
   - `do_tts.py`: This script allows you to speak a single phrase with one or more voices.
     ```bash
     python tortoise/do_tts.py --text "I'm going to speak this" --voice random --preset fast
     ```
   - `faster_inference_read.py`: This script provides tools for reading large amounts of text.
     ```bash
     python tortoise/read_fast.py --textfile <your text to be read> --voice random
     ```
   - `read.py`: This script provides tools for reading large amounts of text.
     ```bash
     python tortoise/read.py --textfile <your text to be read> --voice random
     ```
     This will break up the text file into sentences and then convert them to speech one at a time. It will output a series of spoken clips as they are generated. Once all the clips are generated, it will combine them into a single file and output that as well.

     Sometimes Tortoise may produce a flawed output. You can regenerate any bad clips by rerunning `read.py` with the `--regenerate` argument.

2. To obtain your deepfake, open Wav2Lip.ipynb and follow all the instructions (You should already have an audio recording with a voice from Tortoise).

## Features

- Autonomous deepfake creation on your local machine
- Integration of [Wav2Lip](https://github.com/Rudrabha/Wav2Lip) for lip-sync
- Integration of [Tortoise](https://github.com/neonbjb/tortoise-tts/tree/main) for text-to-speech
- Scripts for scraping videos and audio from YouTube

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

Artur Mistiuk - [mistiuk.artur@gmail.com](mailto:mistiuk.artur@gmail.com)
