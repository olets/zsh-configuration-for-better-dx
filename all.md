## Informative window title

### Terminal.app users

In preferences > Profiles > Window > Title, uncheck everything.

### Everyone

Add this to `~/.zshrc`

```shell
# WINDOW TITLE ---------------

# disable OMZ's title
DISABLE_AUTO_TITLE=”true”

# enable hooks
autoload -U add-zsh-hook

set-window-title-to-dir() {
  # set the window title to
  # <parent dir>/<current dir>

  local title=$(print -P "%2~")
  echo -ne "\033]0;$title\007"
}

set-window-title-to-dir-and-process() {
  # set the window title to
  # <parent dir>/<current dir> - <first word of active command>

  local title=$(print -P "%2~ - ${1[(w)1]}")
  echo -ne "\033]0;$title\007"
}

# update window title before drawing the prompt
add-zsh-hook precmd set-window-title-to-dir

# update the window title before executing a command
add-zsh-hook preexec set-window-title-to-dir-and-process
```

Open a new terminal or run this in already-open terminals

```shell
source ~/.zshrc
```