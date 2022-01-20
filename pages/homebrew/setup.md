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

---

[back](../til.md)
