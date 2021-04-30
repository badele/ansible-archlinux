# ansible-archlinux
Install and configure Archlinux with Ansible

## Pseudo automated installation

We use a [archlinux-auto-install(archlinux LUKS+BTRFS+Ansible installation in UEFI mode)](https://github.com/badele/archlinux-auto-install)

## Vagrant

```
git clone git@github.com:badele/ansible-archlinux.git
cd ansible-archlinux
vagrant up --provision
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
ansible-playbook --limit local dev-i3.yml [--tags tag1,tag2]

# After first run
# Import you GPG with ssh authentification support
update-my-computer
```

## TODO:

- [_] System
  - [x] LUKS
  - [x] Btrfs
    - [_] `snapper`, `snap-pac`
  - [x] `yay`

- [_] Terminal
  - [_] bash trap notification for some scripts (prevent quiet script launched from VM)
  - [x] ZSH
    - [x] move all `ZSH` configuration files to `.config/zsh/` with `ZDOTDIR=$HOME/.config/zsh` in the `~/.zshenv`
    - [x] zinit (alias, bindkey, plugins, etc ...), ZSH customization
    - [x] powerlevel10 prompt
    - [x] `navi` command cheatsheet
    - [x] `fzf` command line fuzzy finder
    - [x] `fd` fast find
    - [x] `ripgrep` fast grep
- [_] Window Manager
  - i3
    - [x] i3-gaps
    - [x] `i3-scrot`
    - [x] polybar
    - [x] wpgtk (Set color scheme from image), generate some files from template (i3, polybar, termite, etc ..)
    - [x] `nerd-fonts-noto-sans-mono` glyph fonts
    - [x] `rofi` app launcher
      [x] `papirus-icon-theme` icon for rofi
  - terminal / tui / cli
    - [x] files managers
      - [_] `ranger` tui - files manager
      - [x] `autojump` cli - go to last used folders with `j` command
      - [_] `trash-cli` cli - move files to trash
    - [_] `peaclock`
    - [x] `neofetch` cli - a command-line system information
    - [_] `newboat`
    - [_] `taskwarrior`
    - [_] `timewarrior`
    - [_] `bashmount`
    - [_] `curseradio`
    - [_] `cava`
    - [_] `bat`
    - [_] `mps-youtube`
    - [_] `spotify-tui`
    - [_] `lazygit`
    - [_] `lazydocker`
    - [_] `calcurse`
    - [_] `ipcalc`
    - [_] `pydoro`
    - [_] `bmenu` system tools
    - [_] `simplescreenrecorder`
    - [_] `gucharmap`
    - [_] `pywal-git`, `colorz`, `wpgtk`
    - [_] `pass`, `browserpass` `browserpass-chrome`
    - [_] `direnv`
    - [_] `mocp`
    - [_] `imv`, `viewnior` image viewver
    - [_] `mpv` video player
    - [_] `oz/tz`
    - [_] activate bitmap font => rm /etc/fonts/conf.d/70-no-bitmaps.conf et vérifier affichage fonte bitmap
  - [_] dev
    - [_] Visual Studio Code
    - [_] `shellcheck`
    - [_] `bats` `shunit2`
    - [_] `asdf` Extendable version manager with support for Ruby, Node.js, Elixir, Erlang & more
    - [_] `diagrams`
    - [_] `neovim`, `xclip` ?, `xsel` ?
    - [_] `clipit`, `greenclip`

  - [_] tools
    - [_] custom scripts
      - [x] `set-color-scheme-from-image` custom script for define color scheme from image filename
      - [_] https://github.com/ko1nksm/ghostplay
      - [_] `aha` convert colored terminal output to HTML
      - [_] `subnetcalc`
      - [_] n8n (domotique)
      - [_] bpytop
      - [_] googler
