# Vim

For my configuration [see here](https://github.com/kanokkorn/config/blob/master/.vimrc)

## Iterate number

Iterate number using vim

```text
0
0
0
0
0
0
```

use ``` g ``` and ``` ctrl+a ``` after visual block highlight all number

result will look like this

```text
1
2
3
4
5
```

## Remove unwated spaces

deletes any trailing whitespace at the end of each line

```vim
:%s/\s\+%//e
```

## Fix indent

typing ```gg=G``` to fix indent whole file

## Open file in new tab

Open file in new tab

```vim
:tabnew filename
```

## Show/Hide number

default vim doesn't show number

```vim
:set number
```

or if not want to

```vim
:set nonumber
```

## Change Colorscheme

Default colors can be quite hard to read. To change colors

```vim
:colo
```

Press ```tab``` to scroll through available colors

## Convert space to tab

What if some program want tab and not space like [makefile](./make.md)

```vim
:set noet|retab!
```

## Autocomplete

Press ```ctrl``` + ```n``` for autocomplete if you typed that word before

## File finder

Press ```ctrl``` + ```x``` and ```ctrl``` + ```f``` for insert file name


## Terminal

Open terminal inside vim

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

Use tree view instead of default view

```vim
:let g:netrw_liststyle = 3
```

### Disable banner

Disable netrw banner if you don't want it

```vim
:let g:netrw_banner = 0
```
