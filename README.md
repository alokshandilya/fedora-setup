<p align="center">
  <span>
      <img src="https://github.com/alokshandilya/fedora-setup/assets/77057272/09491266-a988-4600-aa7a-feeb00baefcb" width="300" height="120">
  </span>
  
  <span>
      <img src="https://github.com/alokshandilya/fedora-setup/assets/77057272/f57736fb-f83c-4a3f-9d4f-7483a389d902" width="300" height="120">
  </span>
</p>

# Steps for Fedora + DWM setup

- `git clone https://github.com/alokshandilya/fedora-setup`

## Touchpad

- run `1-touchpad.sh` script and **_reboot_**
- **Explanation:**
  - edits `/etc/X11/xorg.conf.d/30-touchpad.conf` and adds the following content

    ```bash
    Section "InputClass"
            Identifier "touchpad"
            MatchIsTouchpad "on"
            Driver "libinput"
            Option "Tapping" "on"
            Option "TappingButtonMap" "lrm"
            Option "NaturalScrolling" "on"
            Option "ScrollMethod" "twofinger"
    ```

## Fastest mirror + Parallel downloads

- run `2-fastest-mirror.sh` script
- **Explanation:**
  - edits `/etc/dnf/dnf.conf` and adds the following content

    ```bash
    fastestmirror=1
    max_parallel_downloads=10
    ```

## Fedora upgrade + Firefox + Google login

- `sudo dnf -y upgrade --refresh` and **_reboot_**
- login firefox account and google account
- install `google-chrome` or `microsoft-edge`

## Install DNF packages

- basic + dwm prerequisite packages + fonts

```bash
sudo dnf install git vim neovim gh dash NetworkManager-tui gvfs-mtp make gcc libXft-devel libX11-devel libXinerama-devel imlib2-devel gd-devel lxappearance stow jetbrains-mono-fonts fira-code-fonts fish flameshot redshift zathura rofi zathura-pdf-poppler cascadia-fonts-all conky exa sysstat picom python3-pip cargo twitter-twemoji-fonts fd-find yt-dlp yt-dlp-fish-completion xset zoxide flatpak obs-studio gparted vlc
```

## Configure git

- `git config --global core.editor nvim` **_later change to lvim_**
- `git config --global user.name alokshandilya`
- `git config --global user.email alok.shandilya10@gmail.com`
- `gh auth login`

## Follow Guide

- `https://www.hackingthehike.com/fedora39-guide`

> **Note:** This guide is for Fedora 39, but it works for Fedora 40 as well.

## Firefox GNOME Theme

- `https://github.com/rafaelmardojai/firefox-gnome-theme`

## GTK and Icon Theme

```bash
git clone https://github.com/vinceliuice/Orchis-theme.git
cd Orchis-theme
sudo ./install.sh -t green
```

```bash
git clone https://github.com/vinceliuice/Qogir-icon-theme.git
cd Qogir-icon-theme
sudo ./install.sh
```

## Install Suckless Software

- `dwm`, `dmenu`, `st`, `dwmblocks`

```bash
git clone https://github.com/alokshandilya/suckless
cd dwm
# ./install.sh
```

- copy `.dwm/autostart` to `~/.dwm/autostart`

## Dotfiles

```bash
git clone https://github.com/alokshandilya/dotfiles.git
cd dotfiles
mkdir -p ~/.local/share/applications
mkdir -p ~/.local/bin/scripts
mkdir -p ~/.local/bin/dwmblocks
stow .
```

## Fish Shell

```bash
chsh -s /usr/bin/fish
reboot
```

## Fonts

- download nerd fonts
  - cascadia code [link](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.1/CascadiaCode.zip)
  - fira code [link](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.1/FiraCode.zip)
  - jetbrains mono [link](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.1/JetBrainsMono.zip)
  - unzip to ~/.local/share/fonts

## VsCode + Pycharm + OMF + flatpak

- vscode download rpm

- `https://gruvbox-wallpapers.pages.dev` for wallpaper

- `curl -fsSl https://fnm.vercel.app/install | bash --skip-shell`
- install omf and fish-autovenv2
  - `curl https://raw.githubusercontent.com/oh-my-fish/oh-my-fish/master/bin/install | fish`
  - `omf install https://github.com/dgrant/fish-autovenv2.git`

```bash
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
flatpak install flathub com.spotify.Client
flatpak install flathub org.standardnotes.standardnotes
curl -sS https://starship.rs/install.sh | sh
```

## `git` commit sign

```bash
git config --global init.defaultBranch main
git config --global commit.gpgsign true
```

## TODO

- sudo dnf install polkit-gnome blueman ripgrep intel-media-driver libva-intel-driver thunar-vcs-plugin thunar-volman thunar-media-tags-plugin thunar-archive-plugin
- sudo dnf install tumbler ffmpegthumnailer

- curl https://raw.githubusercontent.com/Schniz/fnm/master/.ci/install.sh | bash -s -- --skip-shell
- curl -sS https://starship.rs/install.sh | sh
- https://github.com/shiftkey/desktop

- complete other commands from chatgpt
- git config --global init.defaultBranch main
- git config --global commit.gpgsign true  
- export GPG_TTY=$(tty)

- https://rpmfusion.org/Howto/NVIDIA

- if facing vscode errors (sudo dnf remove google-noto-color-emoji-fonts)

- add in .vscode/argv.json

```
"disable-hardware-acceleration": true,
"password-store": "gnome"
```
