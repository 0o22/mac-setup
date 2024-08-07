# MacOS Setup

This repository contains my personal configuration and setup for MacOS Sonoma. Follow these steps to replicate the setup on your own machine. **Works on Sonoma 14.6**

## Table of Contents

- [Pre-Installation](#pre-installation)
- [System Settings](#system-settings)
- [Finder Settings](#finder-settings)
- [Safari Settings](#safari-settings)
- [Terminal Setup](#terminal-setup)
- [Installing Homebrew](#installing-homebrew)
- [Application List](#application-list)
- [iTerm2 Settings](#iterm2-settings)
- [SSH Keys Setup](#ssh-keys-setup)
- [Git Config Setup](#git-config-setup)
- [Global .gitignore](#global-gitignore)
- [License](#license)

## Pre-Installation

On initial startup, I disable **ALL** possible features (such as Location Services, Touch ID, etc.), and refuse to use Apple account at all. I don't need any synchronization between devices and I only need my machine to work properly and nothing more. It may be inconvenient for you, but here I am only describing my vision of OS configuration.

## System Settings

### Network

- [x] **Firewall:** Enabled

### Sound

- [ ] **Play sound on startup:** Disabled
- [ ] **Play user interface effects:** Disabled

### General

#### Airdrop & Handoff

- [ ] **Allow Handoff between this Mac and your iCloud services:** Disabled
- [ ] **AirPlay Receiver:** Disabled

#### Date & Time

- [ ] **24-hour time:** Disabled
- [ ] **Show 24-hour time on Lock Screen:** Disabled

### Control Center

- **Automatically hide and show the menu bar:** Always
- **Recent documents, applications, and servers:** None

### Privacy & Security

- [x] **FileVault:** Enabled
- **Extensions**
  - **Sharing**
    - [ ] **Contact Suggestions:** Disabled
    - [ ] **Add to Reading List:** Disabled
    - [ ] **Notes:** Disabled
    - [ ] **Add to Photos:** Disabled

### Desktop & Dock

#### Dock

- **Size:** ~25%
- **Magnification:** ~40%
- [x] **Minimize windows into application icon:** Enabled
- [x] **Automatically hide and show the Dock:** Enabled
- [ ] **Show suggested and recent apps in Dock:** Disabled

#### Desktop & Stage Manager

- [ ] **Show recent apps in Stage Manager:** Disabled

#### Windows

- [x] **Ask to keep changes when closing documents:** Enabled

#### Mission Control

- [x] **Group windows by application:** Enabled

#### Hot Corners

- [ ] Disable all

### Lock Screen

- **Start Screen Saver when inactive:** Never
- [ ] **Show user name and photo:** Disabled

### Passwords

#### Security Recommendations

- [ ] **Detect Leaked Passwords:** Disabled

#### Password Options

- [ ] **AutoFill Passwords and Passkeys:** Disabled
- [ ] **Keychain:** Disabled

### Wallet & Apple Pay

- [ ] **Add Orders to Wallet:** Disabled

### Keyboard

- [ ] **Adjust keyboard brightness in low light:** Disabled
- **Keyboard brightness:** 0

#### Keyboard shortcuts

##### Input sources

- [x] **Select the previous input source:** Option + Command + Space
- [x] **Select next source in input menu:** Command + Space

##### Screenshots

- [ ] Disable all

##### Spotlight

- [ ] Disable all

##### Function Keys

- [x] **Use F1, F2, etc. keys as standard function keys:** Enabled

#### Text Replacements

- [ ] Delete all

#### Input Sources

- [x] **Use the Caps Lock key to switch to and from ABC:** Enabled
- [ ] **Correct spelling automatically:** Disabled
- [ ] **Capitalize words automatically:** Disabled
- [ ] **Show inline predictive text:** Disabled
- [ ] **Add period with double-space:** Disabled
- [ ] **Use smart quotes and dashes:** Disabled
- **For double quotes:** "abc"
- **For single quotes:** 'abc'

### Trackpad

#### Point & Click

- **Tracking speed:** 4 / 9
- [x] **Silent clicking:** Enabled
- [x] **Tap to click:** Enabled

#### Scroll & Zoom

- [ ] **Natural scrolling:** Disabled

#### More Gestures

- **App Expose:** Swipe Down with Three Fingers

## Finder Settings

### General

- [x] **Show these items on the desktop:** Enabled all
- **New Finder windows show:** `Home folder`
- [ ] **Open folders in tabs instead of new windows:** Disabled

### Sidebar

#### Favorites

- [ ] Recents: Disabled
- [ ] AirDrop: Disabled
- [x] Movies: Enabled
- [x] Music: Enabled
- [x] Pictures: Enabled
- [x] Home directory: Enabled

#### Locations

- [ ] iCloud Drive: Disabled
- [x] `<name>`’s MacBook Air: Enabled

### Advanced

- [x] **Show all filename extensions:** Enabled
- [x] **Remove items from the Trash after 30 days:** Enabled
- **When performing a search:** Search the Current Folder

### View Settings

- Open Finder, press the “Show as list” button
- `Command + Shift + .` – Show hidden items

## Safari Settings

### Start Screen

- [ ] Disable all

### Settings

#### Autofill

- [ ] Disable all

#### Passwords

##### Security Recommendations

- [ ] **Detect Leaked Passwords:** Disabled

#### Search

- **Search Engine:** Google
- [ ] **Include search engine suggestions:** Disabled
- [ ] **Smart Search field:** Disable all

#### Advanced

- [x] **Show features for web developers:** Enabled

## Terminal Setup

### Install Oh My ZSH

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Install Plugins

#### autosuggestions

```sh
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

#### zsh-syntax-highlighting

```sh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

#### zsh-fast-syntax-highlighting

```sh
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting
```

#### zsh-autocomplete

```sh
git clone --depth 1 -- https://github.com/marlonrichert/zsh-autocomplete.git $ZSH_CUSTOM/plugins/zsh-autocomplete
```

### Add Plugins to .zshrc

Add the following line to your `.zshrc` file:

```sh
plugins=(git zsh-autosuggestions zsh-syntax-highlighting fast-syntax-highlighting zsh-autocomplete)
```

### Theme Customization

#### Install powerlevel10k

```sh
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

#### Set Theme in .zshrc

Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in your `~/.zshrc`.

#### Install Meslo Nerd Font

On terminal restart, install Meslo Nerd Font. Then, configure the powerlevel10k theme:

```sh
p10k configure
```

- **Prompt style:** Rainbow
- **Character Set:** Unicode
- **Show current time?:** No
- **Prompt Separators:** Angled
- **Prompt Heads:** Sharp
- **Prompt Tails:** Flat
- **Prompt Height:** One line
- **Prompt Spacing:** Compact
- **Icons:** Many icons
- **Prompt Flow:** Concise
- **Enable Transient Prompt?:** Yes
- **Instant Prompt Mode:** Verbose

## Installing Homebrew

Homebrew is a package manager for macOS that simplifies the installation of software. Follow these steps to install Homebrew:

1. **Open Terminal.**

2. **Run the following command to install Homebrew:**

    ```sh
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

3. **After the installation is complete, ensure Homebrew is set up correctly by running:**

    ```sh
    brew --version
    ```

4. **Reload your shell configuration:**

    ```sh
    source ~/.zshrc
    ```

## Application List

### Formulae list

```sh
asdf
bat
fzf
git
go
neovim
nextdns
node
nvm
php
postgresql@14
python@3.12
rust
sqlite
typescript
volta
```

### Cask list

```sh
alt-tab
appcleaner
arc
bitwarden
chatgpt
cloudflare-warp // unable to use with NextDNS
discord
docker
firefox
focusrite-control-2
google-chrome
hiddenbar
iterm2
jetbrains-toolbox
keka
microsoft-edge
monitorcontrol
notion
obs
postman
raycast
rectangle
shottr
slack
stats
telegram
thunderbird
transmission
visual-studio-code
zed
zoom
```

## iTerm2 Settings

### General

#### Startup

- **Window restoration policy:** Only Restore Hotkey Window

#### Closing

- [ ] **Confirm closing multiple sessions:** Disabled
- [ ] **Confirm "Quit iTerm2":** Disabled

#### Selection

- [ ] **Clicking on a command selects it to restrict Find and Filter:** Disabled

### Appearance

#### General

- **Theme:** Minimal

### Profiles

#### Text

- **Font Size:** 16px

#### Colors

- **Color presets: Import…**
  - Import [flat-colors.itermcolors](https://gist.github.com/0o22/4c2d9e71c0bec9af8e7a504195903e4d)
  - Select in Color Presets flat-colors option

#### Terminal

- [ ] **Show mark indicators:** Disabled

#### Keys

- **Key Mappings**
  - Presets: Natural Text Editing

## SSH Keys Setup

### 1. Generate SSH keys

```sh
ssh-keygen -t ed25519 -C "<github_email>" -f ~/.ssh/id_rsa_github
ssh-keygen -t ed25519 -C "<gitlab_email>" -f ~/.ssh/id_rsa_gitlab
```

### 2. Copy keys to GitHub and GitLab

```sh
pbcopy < ~/.ssh/id_rsa_github.pub
# Then paste in GitHub panel

pbcopy < ~/.ssh/id_rsa_gitlab.pub
# Then paste in GitLab panel
```

### 3. Starts the SSH-Agent

```sh
eval `ssh-agent -s`
```

### 4. Add keys to SSH-Agent

```sh
ssh-add ~/.ssh/id_rsa_github
ssh-add ~/.ssh/id_rsa_gitlab
```

### 5. Configuration file

```sh
vim ~/.ssh/config
```

**File** `config`

```sh
Host github.com
  HostName github.com
  PreferredAuthentications publickey
  IdentityFile ~/.ssh/id_rsa_github

Host gitlab.com
  HostName gitlab.com
  PreferredAuthentications publickey
  IdentityFile ~/.ssh/id_ed25519
```

## Git Config Setup

```sh
git config --global user.name "<your_name>"
git config --global user.email "<your_email>"
git config --global core.pager ""
git config --global core.editor "vim"
```

## Global .gitignore

### 1. Create global `.gitignore` file

```sh
vim ~/.gitignore
```

### 2. Insert the following content

```sh
._*
*.pyc
.DS_Store
Desktop.ini
Thumbs.db
.Trashes
.Spotlight-V100
Icon
```

### 3. Add `.gitignore` to Git configuration

```sh
git config --global core.excludesfile ~/.gitignore
```

## Additional Settings

### VS Code and Zed

As Software Engineer, I use Visual Studio Code and Zed as my primary code editors. Here you can find my VS Code and Zed settings:

- [VS Code Settings](https://github.com/0o22/vscode-settings)
- [Zed Settings](https://github.com/0o22/zed-settings)

## License

This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

```
Feel free to customize further or let me know if you need any adjustments!
```
