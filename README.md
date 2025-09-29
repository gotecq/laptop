# GoTECQ
Laptop is a script to set up a macOS environment for web development.

The script is idempotent: It can run multiple times on the same machine safely.
It installs, upgrades, or skips packages
based on what is already installed on the machine.

## Requirements

- macOS Sonoma (14.4) or higher

> [!NOTE]
> Both Apple Silicon and Intel are supported

Older versions may work but aren't regularly tested. This script is tested on the most recent and its previous version.

## Install

Download, review, then execute the script:

```bash
curl --remote-name https://raw.githubusercontent.com/gotecq/laptop/master/mac
less mac
bash mac 2>&1 | tee ~/laptop.log
```

Choose the additional packages when the prompts appear:

```text
Do you want to install Backend's dependencies? [y|N]
Do you want to install Mobile's dependencies? [y|N]
Do you want to install Frontend's dependencies? [y|N]
```

## What it sets up

### Default
[Update later...]

## Customize in `~/.laptop.local`

Your `~/.laptop.local` is run at the end of the Laptop script.
Put your customizations there.
For example:

```sh
#!/bin/sh

cask "dropbox"
cask "firefox"

brew "tree"
```

Write your customizations such that they can be run safely more than once.
See the `mac` script for examples.

Laptop functions such as `fancy_echo`,`brew_install_or_upgrade`,
and `gem_install_or_update` can be used in your `~/.laptop.local`.

See the [wiki](https://github.com/thoughtbot/laptop/wiki)
for more customization examples.


## License

It is free software,
and may be redistributed under the terms specified in the [LICENSE] file.

[license]: LICENSE

