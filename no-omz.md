## Enable auto-`cd`

Add this to `~/.zshrc`:

```shell
setopt auto_cd
```

Open a new terminal or run this in already-open terminals

```shell
source ~/.zshrc
```

## Informative window title

Add this to `~/.zshrc`

```shell
# WINDOW TITLE ---------------

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

## Enable nice completion menus without OMZ

Add this to `~/.zshrc`:

```shell
# MENU COMPLETION ---------------

# Completion options selected from
# https://github.com/ohmyzsh/ohmyzsh/blob/master/lib/completion.zsh
  unsetopt list_beep
  unsetopt menu_complete
  setopt auto_menu
  setopt complete_in_word
  setopt always_to_end
  unsetopt flow_control
  # use menu for completion
  zstyle ':completion:*:*:*:*:*' menu select
  # case- and hyphen/underscore-insensitive completion
  zstyle ':completion:*' matcher-list 'm:{a-zA-Z-_}={A-Za-z_-}' 'r:|=*' 'l:|=* r:|=*'
  # Use caching so that commands like apt and dpkg complete are useable
  zstyle ':completion::complete:*' use-cache 1
  zstyle ':completion::complete:*' cache-path $ZSH_CACHE_DIR
  # colorize completion menu
  zstyle ':completion:*' list-colors ''
  zstyle ':completion:*:*:kill:*:processes' list-colors '=(#b) #([0-9]#) ([0-9a-z-]#)*=01;34=0=01'

# enable completion
autoload -Uz compinit

# turn on completion
compinit
```

Open a new terminal or run this in already-open terminals

```shell
source ~/.zshrc
```

## Enable syntax highlighting without OMZ

### zsh-syntax-highlighting

[zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting) is a widely used highlighter.
You can install it with Homebrew which is convenient!

Run these commands

```shell
brew install zsh-syntax-highlighting
echo "\nsource ${HOMEBREW_PREFIX}/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ~/.zshrc
source ~/.zshrc
```

(Follow the directions Homebrew logs to the terminal if that doesn't work.)



### fast-syntax-highlighting

[fast-syntax-highlighting](https://github.com/zdharma/fast-syntax-highlighting) is the other great option.
The benefit of "fsh" is it supports themeing.

Run these commands, replacing `~/path/to/fsh` with the path you want to clone the plugin to

```shell
git clone https://github.com/zdharma/fast-syntax-highlighting ~/path/to/fsh
echo "\nsource ~/path/to/fsh/fast-syntax-highlighting.plugin.zsh
source ~/.zshrc
```

## Enable suggestions based on history without OMZ

Install [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions): run this

```shell
brew install zsh-autosuggestions
echo "\nsource ${HOMEBREW_PREFIX}/share/zsh-autosuggestions/zsh-autosuggestions.zsh" >> ~/.zshrc
source ~/.zshrc
```

(Follow the directions Homebrew logs to the terminal if that doesn't work.)

## Enable history substring search without OMZ

Install [zsh-history-substring-search](https://github.com/zsh-users/zsh-history-substring-search):

Add this to `~/.zshrc`

```shell
# HISTORY SUBSTRING SEARCH ---------------
bindkey '^[[A' history-substring-search-up
bindkey '^[[B' history-substring-search-down
```

Run these commands

```shell
brew install zsh-history-substring-search
echo "\nsource ${HOMEBREW_PREFIX}/share/zsh-history-substring-search/zsh-history-substring-search.zsh" >> ~/.zshrc
source ~/.zshrc
```

(Follow the directions Homebrew logs to the terminal if that doesn't work.)