# ESP Home Configs

## Setup

**One Time**

```bash
brew install pyenv pyenv-virtualenv
cat <<EOF >> ~/.localrc
export PYENV_VIRTUALENV_DISABLE_PROMPT=1
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
EOF
source ~/.localrc
pyenv virtualenv 3.10.13 esphome-3.10
```

**Each Time**

```bash
pyenv activate esphome-3.10
```

## Build and Flash

```bash
esphome run <config>.yaml
```

## Debugging

Sometimes the compile for ESP-IDF fails after linking. Most often this happens when adding or removing new components (sensors, outputs, etc). The easiest thing to try is to clean and re-compile.

```bash
esphome clean <config>.yaml
esphome run <config>.yaml
```
