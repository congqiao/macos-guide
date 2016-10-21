# Getting Started with OS X

## Essentials

### Homebrew

Install [Homebrew](http://brew.sh/):

```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Add the following lines to the **beginning** of `/etc/paths`:

    /usr/local/sbin
    /usr/local/bin

### Z shell

Install [Z shell](http://www.zsh.org/):

```bash
brew install zsh
```

Install [Oh-My-Zsh](http://ohmyz.sh/):

```bash
curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh
```

Edit `~/.zshrc`:

```bash
# ...
plugins=(brew osx)
# ...
alias bu='brew update && brew upgrade && brew linkapps && brew cleanup --force -s'
alias reset-launchpad='defaults write com.apple.dock ResetLaunchPad -bool true && killall Dock'
alias purge-ds-store='sudo find / -name .DS_Store -delete && killall Finder'
```

Add the following line to the end of `/etc/shells`:

    /usr/local/bin/zsh

Change your shell:

```bash
chsh -s /usr/local/bin/zsh
```

## Development

### git

Install git:

```bash
brew install git
```

### Visual Studio Code

[Download](https://code.visualstudio.com/Download) and install Visual Studio Code.

### Python

Install Python:

```bash
brew install python3
```

or if you absolutely need to use the old Python 2:

```bash
brew install python
```

### JavaScript

Install [Node.js](https://nodejs.org/):

```bash
brew install node
```
