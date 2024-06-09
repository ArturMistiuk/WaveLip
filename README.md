# WaveLip

WaveLip - a fully autonomous deepfake creator on your computer! It combines the [Wav2Lip](https://github.com/Rudrabha/Wav2Lip) and [Tortoise](https://github.com/neonbjb/tortoise-tts/tree/main) models, along with additional scripts for scraping video and audio from YouTube, so you can create a deepfake of any person you are interested in!

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Installation

To install WaveLip, follow these steps:

1. Download the fully prepared project:
[Full Project](https://drive.google.com/file/d/1cdCYiqY-9IYiFrFOTtWYMBBIbrltALYc/view?usp=drive_link)

2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Usage

Here's a basic example of how to use WaveLip:

1. Scrape video and audio from YouTube:
    ```bash
    python scrape_youtube.py --url "https://www.youtube.com/watch?v=example"
    ```

2. Generate a deepfake video:
    ```python
    from wav2lip import Wav2Lip
    from tortoise import Tortoise
    
    # Example code for creating a deepfake
    # Assuming you have preprocessed your input data and loaded models
    
    # Load models
    wav2lip_model = Wav2Lip()
    tortoise_model = Tortoise()
    
    # Generate lip-synced video
    video_path = "path/to/your/video.mp4"
    audio_path = "path/to/your/audio.wav"
    output_path = "path/to/output/deepfake.mp4"
    
    wav2lip_model.generate(video_path, audio_path, output_path)
    
    # Generate speech using Tortoise
    text = "Your text to generate speech"
    tortoise_model.text_to_speech(text, output_path="path/to/output/audio.wav")
    ```

## Features

- Autonomous deepfake creation on your local machine
- Integration of [Wav2Lip](https://github.com/Rudrabha/Wav2Lip) for lip-sync
- Integration of [Tortoise](https://github.com/neonbjb/tortoise-tts/tree/main) for text-to-speech
- Scripts for scraping videos and audio from YouTube

## Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your_feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin feature/your_feature`)
5. Create a new Pull Request

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

Your Name - [your_email@example.com](mailto:your_email@example.com)

Project Link: [https://github.com/your_username/WaveLip](https://github.com/your_username/WaveLip)
