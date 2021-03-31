# vim

vim tips and tricks

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
