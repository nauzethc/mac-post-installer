# Mac Post-installation

## Developer tools
```
xcode-select --install
```

## Homebrew and Cask
```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install caskroom/cask/brew-cask
```

## oh-my-zsh with syntax highlighting
```
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
cd ~/.oh-my-zsh/custom/plugins
git clone git://github.com/zsh-users/zsh-syntax-highlighting.git
```
### zshrc
```bash
plugins=(git osx sudo zsh-syntax-highlighting)

# Disable shared history between shells
setopt no_share_history

# Add hostname on ssh clients
if [ -n "$SSH_CLIENT" ]; then
    PROMPT="$fg_bold[yellow]%m$reset_color $PROMPT"
fi

# Alias
alias server="python -m SimpleHTTPServer"
alias vi="vim"

# Python virtualenvs
export WORKON_HOME=$HOME/.virtualenvs
```

## Dock modifications (speed and delay)
```bash
defaults write com.apple.Dock autohide-delay -float 0
defaults write com.apple.dock autohide-time-modifier -float 0.3
killall Dock
```

## Disable 'last login' message on terminal
```
touch ~/.hushlogin
```

## Unhide Library
```
chflags ~/Library
```

## Generate SSH key and enable agent
```
ssh-keygen
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

## Apps and packages
```bash
brew install wget lftp ssh-copy-id node
brew cask install google-chrome iterm2 atom vlc moom spotify transmission
```

## Atom packages
```bash
apm install oceanic-next linter linter-eslint react pigments
```
