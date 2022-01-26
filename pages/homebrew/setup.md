---
layout: default
---

# Setup Homebrew on M1 Mac

This is to install homebrew on the M1 Mac and setup the ZSH profile.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" && \
echo "PROMPT='%F{yellow}%n%f: %F{red}%.%f %F{green}%$$%f '" > ~/.zshrc && \
echo "export PATH='/opt/homebrew/bin:$PATH'" >> ~/.zshrc && \
echo "export EDITOR=nano" >> ~/.zshrc && \
echo "export VISUAL=$EDITOR" >> ~/.zshrc && \
source  ~/.zshrc
```

Install Rosetta as some applications are not arm64 based.

```bash
sudo softwareupdate --install-rosetta --agree-to-license
```

Log into the Apple App store before running this command.  This will install apps via `mas` that is in the Brewfile.  

```bash
brew bundle install
```

Brewfile

```brewfile
tap "codefresh-io/cli"
tap "homebrew/bundle"
tap "homebrew/cask"
tap "homebrew/core"
tap "mongodb/brew"
brew "awscli"
brew "git"
brew "helm"
brew "jq"
brew "python"
brew "mas"
brew "codefresh-io/cli/codefresh"
cask "aws-vpn-client"
cask "docker"
cask "gpg-suite"
cask "mongodb-compass"
cask "visual-studio-code"
cask "zoom"
mas "Keynote", id: 409183694
mas "Numbers", id: 409203825
mas "Pages", id: 409201541
mas "Slack", id: 803453959
```

---

[back](../til.md)
