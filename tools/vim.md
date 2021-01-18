# Vim

For my configuration [see here](https://github.com/kanokkorn/config/blob/master/.vimrc)

## Show/Hide number

default vim doesn't show number

```vim
set number
```

or if not want to

```vim
set nonumber
```

## Change Colorscheme

Default colors can be quite hard to read. To change colors

```vim
:colo
```

press ```tab``` to scroll through available colors

## Convert space to tab

 what if some program want tab and not space like [makefile](./make.md)

```vim
:set noet|retab!
```

## Terminal

open terminal inside vim 

```vim
:term
```

for verticle

```vim
:vert term
```

## Netrw

### Basic shortcuts

- ```%``` for create new file

- ```d``` for create new directory

- ```s``` for sort

- ```t``` for open new tab

- ```v``` for open verticle split

- ```o``` for open horizotal split

### Tree view

use tree view instead of default view

```vim
let g:netrw_liststyle = 3
```

### Disable banner

disable netrw banner if you don't want it

```vim
let g:netrw_banner = 0
```
