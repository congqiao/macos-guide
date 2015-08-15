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

Install [Homebrew Cask](http://caskroom.io/):

```bash
brew install caskroom/cask/brew-cask
```

Add taps:
```bash
brew tap homebrew/dupes
brew tap caskroom/fonts
brew tap caskroom/versions
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
plugins=(brew brew-cask osx sublime)
# ...
alias bu='brew update && brew upgrade --all && brew linkapps && brew cleanup --force -s'
alias bcu='brew cask update && brew cask install $(brew cask list) && brew cask cleanup'
alias reset-launchpad='rm ~/Library/Application\ Support/Dock/*.db && defaults write com.apple.dock ResetLaunchPad -bool true && killall Dock'
```

## Development

### git

Install git:

```bash
brew install git
```

### Sublime Text

Install [Sublime Text](http://www.sublimetext.com/):

```bash
brew cask install sublime-text3
```

or if you have purchased a license:

```bash
brew cask install sublime-text-dev
```

Install [Package Control](https://packagecontrol.io/).

Install `Theme - Soda`, `SublimeLinter`.

Edit user settings:

```json
{
	"show_encoding": true,
	"show_line_endings": true,
	"soda_folder_icons": true,
	"theme": "Soda Light 3.sublime-theme"
}
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

In Sublime Text, install `SublimeLinter-pep8`.

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

In Sublime Text, install `SublimeLinter-rubocop`.

### JavaScript

Install [Node.js](https://nodejs.org/):

```bash
brew install node
```

Install [eslint](http://eslint.org/):

```bash
npm install -g eslint babel-eslint eslint-plugin-react
```

In Sublime Text, install `Babel`, `SublimeLinter-contrib-eslint`. Set "JavaScript (Babel)" as the default syntax for `.js` and `.jsx` extensions. Edit SublimeLinter user settings:

```json
"syntax_map": {
	"javascript (babel)": "javascript"
}
```

### SCSS

Install [SCSS-Lint](https://github.com/brigade/scss-lint):

```bash
gem install scss_lint
```

In Sublime Text, install `SCSS`, `SublimeLinter-contrib-scss-lint`.

