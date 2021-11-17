# vim

vim tips and tricks

## clear selection

until next search `:noh`

## git commit in virtualine

```
Plug 'tveskag/nvim-blame-line'
autocmd BufEnter * EnableBlameLine
```

## vim-surround

- `ysiW"` surround a WORD with double quotes

## hapoon

Harpoon is awesome

https://github.com/ThePrimeagen/harpoon
https://www.youtube.com/watch?v=Qnos8aApa9g

## align columns with whitespaces

By using column command

```
'<,'>! column -ts\   -o " "
``
Created an alias for that

```
command! -range Columnize <line1>,<line2>! column -ts\   -o " "
```

## camel case to snake case

Tim Pope's Abolish plugin includes mappings for case conversion of the word under the cursor, such as crs and crc to convert to snake case or camel case.


## macros


Recording a macro

Each register is identified by a letter a to z.

To enter a macro, type:

q<letter><commands>q

To execute the macro <number> times (once by default), type:

<number>@<letter>

So, the complete process looks like:
qd 	start recording to register d
... 	your complex series of commands
q 	stop recording
@d 	execute your macro
@@ 	execute your macro again  

## center current line

The z. and zz commands will recenter the line the cursor is on. z. also moves the cursor to the first non-whitespace character in the line, while zz keeps the cursor where it is.

