# Getting Started with OS X

## Essentials

### Homebrew

Install [Homebrew](http://brew.sh/):

```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Add the following lines to the **beginning** of `/etc/paths`:

	/usr/local/bin
	/usr/local/sbin

Add taps:
```bash
brew tap homebrew/dupes
```

### Z shell

Install [Z shell](http://www.zsh.org/):

```bash
brew install zsh
```

Install [Oh-My-Zsh](http://ohmyz.sh/):

```bash
$ curl -L https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh | sh
```

Edit `~/.zshrc`:

```bash
# ...
plugins=(brew osx)
# ...
alias bu='brew update && brew upgrade --all && brew linkapps && brew cleanup --force -s'
alias reset-launchpad='rm ~/Library/Application\ Support/Dock/*.db && defaults write com.apple.dock ResetLaunchPad -bool true && killall Dock'
```

## Development

### git

Install git:

```bash
brew install git
```

### Python

Install Python:

```bash
brew install python3
```

or if you absolutely need to use the old Python 2:

```bash
brew install python
```

Install `pep8`:
```bash
pip3 install pep8
```

### Ruby

Install [rbenv](https://github.com/sstephenson/rbenv):

```bash
brew install rbenv ruby-build
```

Add the following lines to `~/.zprofile`:

```bash
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"
```

Install a Ruby version:

```bash
rbenv install -l
rbenv install $SOME_VERSION
rbenv rehash
rbenv global $SOME_VERSION
```

Install [rubocop](https://github.com/bbatsov/rubocop):

```bash
gem install rubocop
rbenv rehash
```

### JavaScript

Install [Node.js](https://nodejs.org/):

```bash
brew install node
```

Install [eslint](http://eslint.org/):

```bash
npm install -g eslint eslint-plugin-react
```
