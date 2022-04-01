# ZSH Cheatsheat

[zhs](https://www.zsh.org/) is an open-source interactive shell that offers the ability to easily add command line plugins, as well as other features.

### Installation

`zsh` can be installed can be installed by most package managers with the name `zsh`.

```shell
$ atp-get install zsh
$ pacman -S zsh
```

### Make ZSH your main shell

First, find the full path to the `zsh` shell with

```shell
$ cat /etc/shells
```

Then, set the shell using
```shell
$ chsh -s full-path-to-shell
```

More info on changing the default shell can be found [here](https://wiki.archlinux.org/title/Command-line_shell#Changing_your_default_shell).

### Themeing
Find a collection of themes for zsh by [installing OhMyZHS](https://github.com/ohmyzsh/ohmyzsh#getting-started), selecting a  [OhMyZSH Themes](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)

#### Powerlevel10k

An external theme for `zsh` not built into the main selection of themes.

An installation guide for it can be found [here](https://github.com/romkatv/powerlevel10k#installation)

### More Information

More info can be found on the [Arch Linux ZSH documentation page](https://wiki.archlinux.org/title/zsh)

