# 🚀 Shell Velocity

A portable [notational velocity][NV] for your shell written in POSIX shell.

https://user-images.githubusercontent.com/96259932/223130698-f870c17c-f307-40c0-b48f-050173bf3d18.mp4

---

* [Features](#features)
* [Dependencies](#dependencies)
* [Installation](#installation)
  * [Arch Linux (AUR)](#arch-linux-aur)
  * [Manual](#manual)
* [Usage](#usage)
* [Philosophy](#philosophy)

## Features

* Removes cognitive load by combining the note creation and note searching
* Customizable (use your preferred fuzzy finder or file picker. 
  * See [tested pickers](docs/tested-pickers.md)
* Portable (runs on every POSIX compatible OS)
* Minimal (only a POSIX shell and the picker of your choice)
* Nonintrusive (use markdown by default, but works also with your preferred markup languages such as: [org][ORG], [neorg][NORG], [rst][RST], [adoc][ADOC], etc)

## Dependencies

* POSIX compliant shell
* POSIX utils
* [`fzf`][FZF] or your favorite picker (e.g. fzy, rofi, dmenu, etc)

## Installation

### Arch Linux (AUR)

```bash
yay -S shell-velocity-git
```

### Manual

> **Important**
> Make sure that `~/.local/bin` is in your `PATH`.

```bash
mkdir -p ~/.local/bin
curl https://raw.githubusercontent.com/saccarosium/shell-velocity/main/shv -o ~/.local/bin/shv
chmod +x ~/.local/bin/shv
```

## Usage

> **Note** 
> In `docs` you can find the manual in markdown, html and groff. Choose the one you like.

The first design goal of this script is to make creating and searching notes as frictionless as possible. First you run `shv` without subcommands. You will be presented with a grep search of all your notes. Search for what you where looking for and if you don't find it you simply press enter and a new note will be created by your query.


## Philosophy

> The reasoning behind Notational Velocity's present lack of multi-database support is that storing notes in separate databases would 1) Require the same kinds of decisions that category/folder-based organizers force upon their users (e.g., "Is this note going to be work-specific or home-specific?"), and 2) Defeat the point of instantaneous searching by requiring, ultimately, the user to repeat each search for every database in use.
> 
> -- quote,scrod creator of notational_velocity

By providing a default directory, we offer (one) fix to the first issue.

By searching the whole set of directories simultaneously, we handle the second.

It also handles Notational Velocity's issue with multiple databases. UNIX does not allow repeated filenames in the same folder, but often the parent folder provides context, like in `workout/TODO.md` and `coding/TODO.md`.


[NV]: https://notational.net/
[ORG]: https://orgmode.org/
[RST]: https://docutils.sourceforge.io/rst.html
[FZF]: https://github.com/junegunn/fzf
[NORG]: https://github.com/nvim-neorg/neorg
[ADOC]: https://asciidoc.org/
