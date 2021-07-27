# vim

vim tips and tricks

## git commit in virtualine

```
Plug 'tveskag/nvim-blame-line'
autocmd BufEnter * EnableBlameLine
```

## vim-surround

- `ysiW"` surround a WORD with double quotes

## align columns with whitespaces

By using column command

```
'<,'>! column -ts\   -o " "
``
Created an alias for that

```
command! -range Columnize <line1>,<line2>! column -ts\   -o " "
```
