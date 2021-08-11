---
# try also 'default' to start simple
# theme: geist # apple-basic #  # 
# apply any windi css classes to the current slide
# https://sli.dev/custom/highlighters.html
# highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Zsh configuration for better DX
  Small zsh customizations for big productivity gains
---

<style>
  .slidev-layout h2 {
    @apply my-4;
  }
</style>

# Zsh configuration for <br> better DX

Henry Bley-Vroman

Aug 2021

https://github.com/olets/zsh-configuration-for-better-dx

https://zsh-configuration-for-better-dx.vercel.app/

---

# We'll Set Up:

1. VS Code CLI
1. auto-<span class="rounded bg-gray-200 px-2">cd</span>
1. Minimal informative window title
1. Completion menus
1. Syntax highlighting
1. Suggestions based on history
1. History substring search
1. Abbreviations

---

# VS Code CLI

## What?

You can open a directory in VS Code from the command line. It works like this:

```shell
% cd my-project
% code .
# VS Code opens to my-project
```


## How?

> Open the Command Palette (<span class="rounded bg-gray-200 px-2">Cmd+Shift+P</span>) and type 'shell command' to find the Shell Command: Install 'code' command in PATH command.

![VS Code command palette](https://code.visualstudio.com/assets/docs/setup/mac/shell-command.png)

---

# auto-<span class="rounded bg-gray-200 px-2">cd</span>

## What?

Save keystrokes by not typing <span class="rounded bg-gray-200 px-2">cd</span>!

Instead of

```shell
cd my-project
```

just run the command

```shell
my-project
```

Live (😬) demo

## How?

See https://github.com/olets/zsh-configuration-for-better-dx/blob/main/setup.md

---
layout: image-right
image: ./assets/images/window-title.png
---

# Minimal informative window title

## What?

Terminal window titles can say anything you want. And they can be dynamic! I like the format

```shell
<parent dir>/<current dir>[ - <process>]
```

or

```shell
<current dir>[ - <process>]
```

## How?

See https://github.com/olets/zsh-configuration-for-better-dx/blob/main/setup.md


---
layout: image-right
image: ./assets/images/syntax-highlighting.png
---


# Syntax highlighting

## What?

You can have syntax highlighting in your shell.
This is helpful even if you're just running basic commands:
misspelled commands will be one color,
correctly spelled commands will be another.

## How?

See https://github.com/olets/zsh-configuration-for-better-dx/blob/main/setup.md


---
layout: image-right
image: ./assets/images/autosuggestions.png
---

# Suggestions based on history

## What?

"autosuggestions" give you quick access to commands you've run before.

Start typing. The buffer will be checked against the command history, and matches will be suggested (in low-saturation type).

Press the right arrow to accept a suggestion.

## How?

See https://github.com/olets/zsh-configuration-for-better-dx/blob/main/setup.md

---

# History substring search

## What?

By default, the up and down arrows cycle through history.

Oh My Zsh users: start typing,
then use up/down to cycle through history entries which _start with_ the typed string.

With **history substring search**: start typing,
then use up/down to cycle through history entries which _contain_ the typed string!

Live (😬) example

## How?

See https://github.com/olets/zsh-configuration-for-better-dx/blob/main/setup.md

---

# Abbreviations

## What?

Abbreviations are a relative of aliases.
The difference is they automatically expand!

### Benefits

- modifiable: you aren't stuck with that one alias you wrote
- doesn't get in the way of memory: the meaning of your shorthands isn't lost
- actively helps memory and learning CLI: visual enforcement of the full command every time you write the shorthand
- save keystrokes!

Live (😬) example

## How?

See https://github.com/olets/zsh-configuration-for-better-dx/blob/main/setup.md
