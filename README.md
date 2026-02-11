# dwm build (current state)

This repository contains the current source and config for a patched `dwm` build.

## Active behavior

- `MODKEY` is `Super` (`Mod4Mask`).
- Terminal command is `terminator`.
- App launcher is `dmenu_run`.
- Tags are `0` through `10` (11 total tags).
- Layouts compiled in:
- `[]=` tile
- `><>` floating
- `[M]` monocle
- `HHH` grid

## Included patches/features in code

- alpha (bar transparency)
- attachaside
- cyclelayouts
- gridmode
- restartsig
- rotatestack
- statuspadding
- uselessgap
- autostart (`~/.dwm/autostart_blocking.sh` then `~/.dwm/autostart.sh`)

## Dependencies

From `PKGBUILD`:

- `libx11`
- `libxinerama`
- `libxft`
- `ttf-hack`
- `ttf-joypixels`
- `freetype2`
- `st`
- `dmenu`
- `tabbed`

Font config in `config.h` also references:

- `Mononoki Nerd Font`
- `Source Code Pro Bold`
- `JoyPixels`

## Build

```bash
make
sudo make install
```

## Keybindings (active in `config.h`)

| Keybinding | Action |
| :--- | :--- |
| `Super + Enter` | Open terminal (`terminator`) |
| `Super + Shift + Enter` | Open launcher (`dmenu_run`) |
| `Super + b` | Toggle bar |
| `Super + j` | Focus next window in stack |
| `Super + k` | Focus previous window in stack |
| `Super + Shift + j` | Rotate stack forward |
| `Super + Shift + k` | Rotate stack backward |
| `Super + i` | Increase number of master clients |
| `Super + d` | Decrease number of master clients |
| `Super + h` | Decrease master area size (`-0.05`) |
| `Super + l` | Increase master area size (`+0.05`) |
| `Super + Ctrl + Enter` | Zoom (promote focused client) |
| `Super + Tab` | `view {0}` and `cyclelayout -1` (both are bound) |
| `Super + Shift + Tab` | Cycle layout forward |
| `Super + Space` | Toggle current/previous layout |
| `Super + Shift + Space` | Toggle floating for focused window |
| `Super + t` | Set tile layout |
| `Super + f` | Set floating layout |
| `Super + m` | Set monocle layout |
| `Super + g` | Set grid layout |
| `Super + ,` | Focus previous monitor |
| `Super + .` | Focus next monitor |
| `Super + Shift + ,` | Send focused window to previous monitor |
| `Super + Shift + .` | Send focused window to next monitor |
| `Alt + Ctrl + m` | Run `terminator -e bpytop` |
| `Alt + Ctrl + p` | Run `passmenu` |
| `Alt + Ctrl + c` | Run `chromium` |
| `Alt + Ctrl + e` | Run `emacs` |
| `Alt + Ctrl + i` | Run `flameshot gui` |
| `Super + Shift + q` | Quit dwm |
| `Super + Shift + r` | Restart dwm |

Tag bindings (`KEY` in `` ` ``, `1`..`9`, `0`) - 11 total tags (`0` through `10`):

- `Super + KEY` -> view tag
- `Super + Ctrl + KEY` -> toggle view of tag
- `Super + Shift + KEY` -> move focused client to tag
- `Super + Ctrl + Shift + KEY` -> toggle focused client on tag

## Notes

- `config.h` is the active config used for this build.
- `config.def.h` is a template/default config.
