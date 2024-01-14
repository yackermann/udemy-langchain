Langchain Udemy
===

This is my code for the Damien Benveniste [Langchain Udemy course](https://www.udemy.com/course/introduction-to-langchain/).

This code is here as great reference in case something does not work, but it worked for me, or was fixed by me while doing the course.

## Setup

1. Create `virtualenv` for python@3.10 and activate it

```bash
# For MacOS
virtualenv -p /opt/homebrew/bin/python3.10 venv

source ./venv/bin/activate
```

2. Install deps

```bash
pip install -r requirements.txt
```

3. Rename `example.env` to `.env` and fill API key details

## Additional Notes

- FAISS is failing to install

Lower python version to 3.10. Or creat venv that is 3.10.

- Failing to install "python-poppler" on MacOS?

Install system dependencies:

```bash
brew install pkg-config poppler
```

- GitLSF is missing (MacOS)

```bash
brew install git-lfs
```

- Missing tesseract

```bash
brew install tesseract
```

- Pygraphviz is failing to install

See <https://stackoverflow.com/questions/40266604/pip-install-pygraphviz-fails-failed-building-wheel-for-pygraphviz>

And this: <https://github.com/pygraphviz/pygraphviz/issues/11#issuecomment-1876025261>

```bash
brew install graphviz

pip install graphviz

pip install --no-cache-dir \
  --config-settings="--global-option=build_ext" \
  --config-settings="--global-option=-I$(brew --prefix graphviz)/include/" \
  --config-settings="--global-option=-L$(brew --prefix graphviz)/lib/" \
  pygraphviz
```

- [MacOS] PyAudio fails to install

```bash
brew install portaudio
pip3 install pyaudio
```

- In S10 `recognize_whisper_api` is erroring with `openai.lib._old_api.APIRemovedInV1:`

`speech_recognition` package is using old OpenAI API that needs updating. See PR https://github.com/Uberi/speech_recognition/pull/729

If you still have this issue, you can simply copy the change from the PR to your package.

- FFMpeg not found

```bash
brew install ffmpeg
```