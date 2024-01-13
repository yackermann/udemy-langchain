Langchain Udemy
===

This is my code for the Damien Benveniste [Langchain Udemy course](https://www.udemy.com/course/introduction-to-langchain/).

This code is here as great reference in case something does not work, but it worked for me, or was fixed by me while doing the course.

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

See https://stackoverflow.com/questions/40266604/pip-install-pygraphviz-fails-failed-building-wheel-for-pygraphviz

And this: https://github.com/pygraphviz/pygraphviz/issues/11#issuecomment-1876025261


```bash
brew install graphviz

pip install graphviz

pip install --no-cache-dir \
  --config-settings="--global-option=build_ext" \
  --config-settings="--global-option=-I$(brew --prefix graphviz)/include/" \
  --config-settings="--global-option=-L$(brew --prefix graphviz)/lib/" \
  pygraphviz
```