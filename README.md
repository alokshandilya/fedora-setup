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

- `sudo dnf -y upgrade --refresh`
- login firefox account and google account
- install `google-chrome` or `microsoft-edge`
