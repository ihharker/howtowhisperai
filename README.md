# How do Whisper AI?
This repo details how to install and get started with Whisper AI for transcription.

## Python Setup
This guide assumes you are using one of the major Python versions 3.11, 3.10, or 3.9.  

> ¡¡¡WhisperAI does not currently support 3.12!!!

You can verify you have a correct version in a terminal as follows

  ```
  python -V
  Python 3.11.6
  ```

[Python 3.11 Download](https://www.python.org/downloads/release/python-3116/)

## Installation

WhisperAI depends on [FFMPEG](https://ffmpeg.org/), which needs to be installed on your system.
FFmpeg is used here for converting various types of media into a common format the AI can understand.

### Windows FFMPEG Install

I personally recommend [Scoop](https://scoop.sh/), a package manager for Windows.  
Scoop will install packages and apps, and allow you to use these apps on the terminal and elsewhere.

> Scoop Install (from scoop.sh) {Terminal}
> ```
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser # Optional: Needed to run a remote script the first time
> irm get.scoop.sh | iex
> ```

> Scoop FFMPEG Install {Terminal}
> ```
> scoop install ffmpeg
> ```

### Mac FFMPEG Install

I personally recommend [Homebrew](https://brew.sh/), a package manager for Mac.
Brew will install packages and apps, and allow you to use these apps on the terminal and elsewhere.

> Brew Install (from brew.sh) {Terminal}
> ```
> /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
> ```

> Brew FFMPEG Install {Terminal}
> ```
> brew install ffmpeg
> ```

### Ubuntu FFMPEG Install

> ```
> sudo apt update && sudo apt install ffmpeg
> ```

### WhisperAI Install

Once you've installed ffmpeg and python, you can install Whisper AI using pip in the terminal!
> ```
> pip install -U openai-whisper
> ```
The `-U` flag here is used for installing the latest `openai-whisper` package, in the event your local  
installation is outdated.

Congratulations! Now we can get started with some Python code.

## WhisperAI Python Usage

Below is an example script to transcribe every .wav in the current directory.
```
import whisper
import os

model = whisper.load_model("small.en")

for infile in os.listdir():
    # f = filename
    # e = extenstion (.wav)
    f, e = os.path.splitext(infile)

    # if guard
    # ignore any files not ending in .wav 
    if (e != ".wav"):
        continue

    outfileName = f + ".txt"
    outfile = open(outfileName, 'w')

    result = model.transcribe(infile)
    # print(result["text"])
    print(result["text"], file=outfile)
```

## WhisperAI Commmand-Line Usage

Transcribe all files ending in .wav in the current directory.
```
whisper ./*.wav --model small.en -f txt
```

## Further Research

Audio files need to be trimmed, Whisper will interpret silence as garbage  
and the garbage persists into future transcription like a feedback loop

Model tiny.en may not be enough for our usage, compare models base.en and small.en

I can write a script to match the Alexa script, the rest being the participant  
This script would also format the ai output


