# How do I Whisper AI?
This repo details how to install and get started with Whisper AI for transcription.

## Python Setup
This guide assumes you are using one of the major Python versions 3.11, 3.10, or 3.9.  

> WhisperAI does not currently support 3.12!

You can verify you have a correct version in a terminal as follows

  ```
  > python -V
  Python 3.11.6
  ```

[Python 3.11 Download](https://www.python.org/downloads/release/python-3116/)

## Installation

WhisperAI depends on [FFMPEG](https://ffmpeg.org/), which needs to be installed on your system.

### Windows FFMPEG Install

I personally recommend [Scoop](https://scoop.sh/), a package manager for Windows.  
Scoop will install packages and apps, and allow you to use these apps on the terminal and elsewhere.

> Scoop Install (from scoop.sh) {Terminal}
```
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser # Optional: Needed to run a remote script the first time
> irm get.scoop.sh | iex
```

> Scoop FFMPEG Install {Terminal}
  scoop install ffmpeg

### Mac FFMPEG Install

I personally recommend [Homebrew](https://brew.sh/), a package manager for Mac.
Brew will install packages and apps, and allow you to use these apps on the terminal and elsewhere.

> Brew Install (from brew.sh) {Terminal}
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

> Brew FFMPEG Install {Terminal}
  brew install ffmpeg

### Ubuntu FFMPEG Install

  sudo apt update && sudo apt install ffmpeg


