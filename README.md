# Steps for Fedora + DWM setup

- `git clone https://github.com/alokshandilya/fedora-setup`

## Touchpad

- run `1-touchpad.sh` script
- edit `/etc/X11/xorg.conf.d/30-touchpad.conf` and add the following content

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
