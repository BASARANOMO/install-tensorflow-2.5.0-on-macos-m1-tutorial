# Install Tensorflow 2.5.0 on Mac OS (Apple M1 Silicon): a Brief Tutorial

## Xcode and CLI Tools

- Install __Xcode__ from Apple App Store

- Download and install __Xcode Command Line Tools__:

  ```shell
  xcode-select --install
  ```

## Homebrew

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

In __~/.zprofile__:

```
eval "$(/opt/homebrew/bin/brew shellenv)"
alias abrew='arch -arm64 /opt/homebrew/bin/brew'
alias ibrew='arch -x86_64 /usr/local/bin/brew'

export PATH="/opt/homebrew/bin/git:${PATH}"
```

## Python and virtual envs

```shell
brew install pyenv

brew install pyenv-virtualenv
```

Need to configure __~/.zshrc__, __~/.bash_profile__ or __~/.zprofile__.

In __~/.zshrc__:
```
eval "$(pyenv init -)"
source ~/.zprofile
source ~/.bash_profile
```

In __~/.bash_profile__:

```
if which pyenv-virtualenv-init > /dev/null; then eval "$(pyenv virtualenv-init -)"; fi
```

In __~/.zprofile__:

```
export PYENV_ROOT="$HOME/.pyenv"

eval "$(pyenv init --path)"
```

Then:

```shell
pyenv install miniforge3-4.10.1-5

pyenv shell miniforge3-4.10.1-5

conda create --name tensorflow-macos python=3.9.5

conda activate tensorflow-macos
```

## Tensorflow-macos and Tensorflow-metal
```
conda install -c apple tensorflow-metal

pip install tensorflow-macos

pip install tensorflow-metal
```

