## Enable nicer completion menus with OMZ

Add this to `~/.zshrc`:

```shell
# MENU COMPLETION ---------------

HYPHEN_INSENSITIVE=true
```

Open a new terminal or run this in already-open terminals

```shell
source ~/.zshrc
```

## Enable syntax highlighting with OMZ

### zsh-syntax-highlighting

[zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting) is a widely used highlighter.
You can install it with Homebrew which is convenient!

```shell
git clone --depth=1 https://github.com/zsh-users/zsh-syntax-highlighting ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
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

```shell
git clone --depth=1 https://github.com/zdharma/fast-syntax-highlighting ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting
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

## Enable suggestions based on history with OMZ

Install [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions): run this

```shell
git clone --depth=1 https://github.com/zsh-users/zsh-autosuggestions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
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

## Enable history substring search with OMZ

Install [zsh-history-substring-search](https://github.com/zsh-users/zsh-history-substring-search): Run this


```shell
git clone --depth=1 https://github.com/zsh-users/zsh-history-substring-search ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-history-substring-search
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


