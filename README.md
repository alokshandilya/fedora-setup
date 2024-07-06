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
