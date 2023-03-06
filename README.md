# :rocket: Shell Velocity

![demo](assets/demo.mov)

A portable notational velocity for your shell written in `bash`.

## Feauteres

* Removes cognitive load by combining the note creation and note searching
* Customizable (use your preffered fuzzy finder or file picker; see [tested pickers](https://github.com/saccarosium/shell-velocity/wiki/Tested-Pickers))
* Uses wather editor you want (even [Visual Studio Code]()!)
* Portable (runs everywhere bash run, even on the preinstalled one on OSX)
* Minimal (only requires bash and a picker of your choice)

## Dependencies

* `bash 3.2+`
* UNIX commands
* [`fzf`](https://github.com/junegunn/fzf) or your favorite picker (e.g. fzy, rofi, dmenu, etc)

## Installation

Make sure that `~/.local/bin` is in your `PATH`.

```bash
mkdir -p ~/.local/bin
curl https://raw.githubusercontent.com/saccarosium/shell-velocity/main/shv -o ~/.local/bin/shv
chmod +x ~/.local/bin/shv
```

## Usage

```bash
shv # select a note
shv tags # list all notes with specific tag
shv diary # select a note from diary folder
shv <today | t> # edit todays diary note
shv <tomorrow | tom | tm> # edit tomorrow diary note
shv <yesterday | ye | y> # edit yesterday diary note
```

## Customization

> **note**
> The values of the variables below are the defaults.

> **warning**
> All the been used here needs to be POSIX compatible.

```bash
# Path to notes
export SHV_PATH="$HOME/Documents/notes"

# Path to diary
export SHV_DIARY_PATH="$SHV_PATH/diary"

# Regex used for searching tags
# By default markdown tags '#tag'
export SHV_TAG_EXPR="#[a-z0-9_]+"

# String passed to 'date' command.
# For see how to modify this value check 'man date'
export SHV_DATE_FMT="%Y-%m-%d"

# Exention used for the notes
export SHV_EXT="md"

# Picker used to select notes
export SHV_PICKER="fzf --ansi --print-query --bind=ctrl-g:print-query"
```
