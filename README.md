# What is OpenAI Whisper?

OpenAI Whisper is an automatic speech recognition (ASR) system developed by OpenAI. It is designed to transcribe spoken language into text with high accuracy. Whisper is trained on a large and diverse dataset of multilingual and multitask supervised data, which enables it to handle various languages, accents, and domains. It can also perform tasks like language identification, translation, and transcription of audio files.

### Key Features of OpenAI Whisper:

1. **Multilingual Support**: It can understand and transcribe multiple languages, making it versatile for global applications.
2. **Robust to Accents and Noise**: Whisper is trained on a wide range of audio data, which includes diverse accents and background noises, making it robust in challenging audio conditions.
3. **Multitask Capabilities**: Beyond just transcription, it can also identify the spoken language, detect different speakers, and even translate between some languages.
4. **High Accuracy**: Due to its extensive training dataset, Whisper can achieve high levels of accuracy in transcription, especially in comparison to traditional ASR systems.
5. **Open-Source**: Whisper is available as an open-source model, allowing developers to integrate it into their applications and further adapt it for specific use cases.

Overall, Whisper is a powerful tool for converting spoken language into text, useful for applications such as transcribing meetings, generating subtitles, voice-activated commands, and more.

# Steps to install and use OpenAI Whisper for video and audio files transcription

Follow these steps to install and use OpenAI Whisper for video and audio files transcription.
`Have fun 😉`

## Needed Links

- [Python](https://www.python.org/)
- [PyTorch - Get Started Locally](https://pytorch.org/get-started/locally/)
- [Chocolatey](https://chocolatey.org/)

## Installing Python

- Visit the [Python website](https://www.python.org/) and download the latest version.

## Installing PyTorch

- Go to the [PyTorch Start Locally page](https://pytorch.org/get-started/locally/) to configure the installation command based on your system and requirements.

### Example Installation Commands:

- **Using CPU**:
  ```bash
  pip3 install torch torchvision torchaudio
  ```
- **Using CUDA 11.8 (NVIDIA GPUs)**:
  ```bash
  pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
  ```

## Installing Chocolatey

- Open PowerShell as Administrator and run the following command:
  ```powershell
  Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
  ```

## Installing FFmpeg

- Use Chocolatey to install FFmpeg for reading various audio files:
  ```powershell
  choco install ffmpeg
  ```

## Installing OpenAI Whisper

Install Whisper:

```bash
pip install -U openai-whisper
```

- For more information about Whisper models, visit the [Whisper GitHub repository](https://github.com/openai/whisper).

## Set this environment to variable to prevent downloading the models again:

```bash
exoprt XDG_CACHE_HOME="C:\Users\<USERNAME>\.cache"
```

Do not forget to change `<USERNAME>` to your username.

## Transcribing Video or Audio Files

- **Default Transcription**:
  ```bash
  whisper file_name1 file_name2 file_name3
  ```
- **Specify a Model**:
  ```bash
  whisper file_name --model medium
  ```
- **Specify a Downloaded Model (Prevent Downloading the model again if environment variable is not set)**:
  ```bash
  whisper file_name --model medium --model_dir C:\Users\<USERNAME>\.cache\whisper
  ```
- **Specify English-only Model**:
  ```bash
  whisper file_name --model medium.en
  ```
- **Specify Language**:
  ```bash
  whisper file_name --language German
  ```
- **Translate to English**:
  ```bash
  whisper file_name --task Translate
  ```
- **Get just the srt file**:
  ```bash
  whisper file_name --model medium --output_format srt
  ```
