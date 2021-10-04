# ansible-archlinux
Install and configure Archlinux with Ansible

## Pseudo automated installation

We use a [archlinux-auto-install(archlinux LUKS+BTRFS+Ansible installation in UEFI mode)](https://github.com/badele/archlinux-auto-install)

## Vagrant

```
git clone git@github.com:badele/ansible-archlinux.git
cd ansible-archlinux
vagrant up --provision

# Enter vagrant LUKS password (warning keyboard disposition)
```

## Host

```
# From fresh archlinux installation
# nmcli device wifi list
# nmcli device wifi connect SSID_or_BSSID password password
cd /tmp/
git clone https://github.com/badele/ansible-archlinux.git
cd ansible-archlinux/ansible
ansible-galaxy install -r galaxy_requirements.yml
ansible-playbook --limit work dev-i3.yml [--tags tag1,tag2] [--check] [--diff]

# After first run, logon in a shell (ZSH plugins installing automatically)
set-color-scheme-from-image

# Import you GPG with ssh authentification support
update-my-computer
```

## TODO:

- [_] System
  - [x] LUKS
  - [x] Btrfs
    - [x] `snapper`, `snap-pac`
  - [x] `yay`
  - [x] gpg ssh agent

- [x] Terminal
  - [x] ZSH
    - [x] move all `ZSH` configuration files to `.config/zsh/` with `ZDOTDIR=$HOME/.config/zsh` in the `~/.zshenv`
    - [x] zinit (alias, bindkey, plugins, etc ...), ZSH customization
    - [x] powerlevel10 prompt
    - [x] `grc` colored command outputs
    - [x] `bat` colored cat clone
    - [x] `exa` ls alternative
    - [x] `navi` command cheatsheet
    - [x] `fzf` command line fuzzy finder
    - [x] `fd` fast find
    - [w] `up` realtime pipe
    - [x] `ripgrep` fast grep
    - [x] `autojump` cli - go to last used folders with `j` command
    - [x] `neofetch` cli - a command-line system information

- [x] Window Manager
  - i3
    - [x] `i3-gaps`
    - [x] `i3-scrot`
    - [x] `polybar`
    - [x] `dunst` notification sytem
    - [x] `gtk-engine-murrine`, `wpgtk`, `colorz` (Set color scheme from image), generate some files from template (i3, polybar, termite, etc ..)
    - [x] `nerd-fonts-noto-sans-mono` glyph fonts
    - [x] `rofi` app launcher
    - [x] `papirus-icon-theme` icon for rofi
    - [x] `arandr`, `autorandr` monitorlayout and auto layout

  - [w] editors

  - [_] Terminal / TUI
    - [w] `neovim` editor
      - [w] `vimplug`
    - [x] `ranger` tui - files manager
      - [_] `trash-cli` cli - move files to trash
    - [x] `wtfutil`
    - [x] `bashtop`
    - [x] `lazygit`, `tig`
    - [x] `lazydocker`
    - [x] `cava`

  | [_] miscs
    - [_] `rokeys` show keys shorcuts
    - [x] `peaclock`
    - [_] `newsboat`
    - [x] `taskwarrior`
    - [x] `bashmount`
    - [_] `curseradio`
    - [_] `mps-youtube`
    - [_] `calcurse`
    - [_] `pydoro`
    - [_] `bmenu` system tools
    - [_] `simplescreenrecorder`
    - [x] `gucharmap`
    - [x] `pass`, `browserpass` `browserpass-chrome` **Note:** In chrome, use `/home/badele/.local/bin/launch-gpg` bin path 
    - [x] `direnv`
    - [_] `mocp`
    - [x] `nomacs`, image viewver
    - [x] `mpv` video player
    - [_] `oz/tz`
    - [_] `automount`
    - [_] activate bitmap font => rm /etc/fonts/conf.d/70-no-bitmaps.conf et vérifier affichage fonte bitmap
  - [_] dev
    - [x] Visual Studio Code
    - [x] `shellcheck`
    - [_] `bats` `shunit2`
    - [x] `asdf` Extendable version manager with support for Ruby, Node.js, Elixir, Erlang & more

  - [_] tools
    - [x] `subnetcalc`
    - [x] `inxi -F` hardware information
    - [_] custom scripts
      - [x] `set-color-scheme-from-image` custom script for define color scheme from image filename
      - [x] `mixer` Update volume and send notification
      - [_] https://github.com/ko1nksm/ghostplay
      - [_] `aha` convert colored terminal output to HTML
      - [_] n8n (domotique)
      - [_] bpytop
      - [_] googler

