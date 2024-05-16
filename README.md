# Dots

Manage your dotfiles without shenanigans.
- No symlinks
- No complex setups
- Just brute force rsync.

## Installation
1. Clone the repo where you want to keep you dotfiles repo:
```bash
git clone git@github.com:thales-maciel/dots.git && \
    cd dots && \
    rm -rf .git && \
    git init
```

2. Edit the `dots.conf` file with the globs you want to include.
Make sure to include parent directories. For example:
```conf
.bashrc
.config/ # this is needed if we want something from this directory
.config/alacritty/
.config/alacritty/alacritty.toml
.config/nvim/*** # this matches everything under .config/nvim/
```
**make sure to include trailing slashes to specify directories**

## Usage
Pull dotfiles from `$HOME` to the current directory:
```bash
./dots in
```

Push dotfiles from the current directory to `$HOME`:
```bash
./dots out
```

Run dry to check config:
```bash
./dots in --dry-run
./dots out --dry
./dots out -d
```

## Requirements
[rsync](https://github.com/RsyncProject/rsync) must be installed.
You probably already have it installed.

