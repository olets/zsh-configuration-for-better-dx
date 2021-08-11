## auto-`cd`

### Without OMZ

Add this to `~/.zshrc`:

```shell
setopt auto_cd
```

Open a new terminal or run this in already-open terminals

```shell
source ~/.zshrc
```

### With OMZ

You already have this.

## Informative window title

### Without OMZ

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

> Terminal.app users will also need to change the default app preferences:
> Preferences > Profiles > Window > Title --> uncheck everything.

### With OMZ

Same as above, and add this to `~/.zshrc`

```shell
DISABLE_AUTO_TITLE=”true”
```

## Completion menus

### Without OMZ

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

### With OMZ

Add this to `~/.zshrc`:

```shell
# MENU COMPLETION ---------------

HYPHEN_INSENSITIVE=true
```

Open a new terminal or run this in already-open terminals

```shell
source ~/.zshrc
```


## Syntax highlighting

### zsh-syntax-highlighting

[zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting) is a widely used highlighter.

#### Without OMZ

Run these commands

```shell
brew install zsh-syntax-highlighting
echo "\nsource ${HOMEBREW_PREFIX}/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ~/.zshrc
source ~/.zshrc
```

(Follow the directions Homebrew logs to the terminal if that doesn't work.)

#### With OMZ

```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

In `~/.zshrc`, add `zsh-syntax-highlighting` to `plugins`. Will look something like

```shell
plugins=(
  # ...
  zsh-syntax-highlighting
  # ...
)
```

Open a new terminal or run this in already-open terminals

```shell
source ~/.zshrc
```

### fast-syntax-highlighting

[fast-syntax-highlighting](https://github.com/zdharma/fast-syntax-highlighting) is the other great option.
The benefit of "fsh" is it supports themeing.

#### Without OMZ

Run these commands, replacing `~/path/to/fsh` with the path you want to clone the plugin to

```shell
git clone https://github.com/zdharma/fast-syntax-highlighting ~/path/to/fsh
echo "\nsource ~/path/to/fsh/fast-syntax-highlighting.plugin.zsh
source ~/.zshrc
```

#### With OMZ

```shell
git clone https://github.com/zdharma/fast-syntax-highlighting ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting
```

In `~/.zshrc`, add `fast-syntax-highlighting` to `plugins`. Will look something like

```shell
plugins=(
  # ...
  fast-syntax-highlighting
  # ...
)
```

Open a new terminal or run this in already-open terminals

```shell
source ~/.zshrc
```

## Suggestions based on history

Install [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)!

### Without OMZ

Run this

```shell
brew install zsh-autosuggestions
echo "\nsource ${HOMEBREW_PREFIX}/share/zsh-autosuggestions/zsh-autosuggestions.zsh" >> ~/.zshrc
source ~/.zshrc
```

(Follow the directions Homebrew logs to the terminal if that doesn't work.)

### With OMZ

Run this

```shell
git clone https://github.com/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

In `~/.zshrc`, add `/zsh-autosuggestions` **at the end** of `plugins`. Will look something like

```shell
plugins=(
  # other plugins, except for  history-substring-search (see below)
  zsh-autosuggestions
)
```

Open a new terminal or run this in already-open terminals

```shell
source ~/.zshrc
```

## History substring search

Install [zsh-history-substring-search](https://github.com/zsh-users/zsh-history-substring-search)!

### Without OMZ

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

### With OMZ

Run this


```shell
git clone https://github.com/zsh-users/zsh-history-substring-search ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-history-substring-search
```

In `~/.zshrc`, add `history-substring-search` **at the end** of `plugins`. Will look something like

```shell
plugins=(
  # other plugins, potentially including zsh-syntax-highlighting
  history-substring-search
)
```

Open a new terminal or run this in already-open terminals

```shell
source ~/.zshrc
```



## Abbreviations

Install [zsh-abbr](https://github.com/olets/zsh-abbr)!

### Without OMZ

```shell
brew install olets/tap/zsh-abbr
echo "\nsource #{HOMEBREW_PREFIX}/share/zsh-abbr/zsh-abbr.zsh" >> ~/.zshrc
source ~/.zshrc
```

### With OMZ



Run this


```shell
git clone https://github.com/olets/zsh-abbr ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-abbr
```

In `~/.zshrc`, add `zsh-abbr` to `plugins`. Will look something like

```shell
plugins=(
  # other plugins
  zsh-abbr
  # other plugins, potentially including zsh-syntax-highlighting and/or history-substring-search
)
```

Open a new terminal or run this in already-open terminals

```shell
source ~/.zshrc
```

### Usage

```shell
% abbr hw="echo hello world"
% hw<SPACE><RETURN> # expands to `echo hello world`!
hello world
% hw<RETURN> # expands to `echo hello world` before running!!
hello world
% abbr e hw # *e*rases the abbreviation
% hw<RETURN>
zsh: command not found: hw
```

Create abbreviation from all your aliases. Aliases will now expand.

```shell
% abbr import-aliases
```

Create abbreviation for all your Git aliases. Git aliases will now expand.

```shell
% abbr import-git-aliases
```