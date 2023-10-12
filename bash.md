## FZF-like in pure bash

```bash
#!/bin/bash

bash_fzf_not_fuzzy() {
    acc=""
    choices="$*"
    choices2="$*"
    while true
    do
        clear >&2
        echo "$choices2" >&2
        echo >&2
        echo -en "\nfilter: $acc" >&2
        read -rsn1 key >&2
        if [[ "$key" == '' ]]
        then
            echo "$choices" | grep "$acc" | tail -1
            return
        elif [[ "$key" == $'\x7f' ]]
        then
            acc="${acc%?}"
        else
            acc="$acc$key"
        fi
        choices2=$(echo "$choices" | grep --color=always "$acc")
    done
}

result=$(bash_fzf_not_fuzzy "$(ls)")
clear
clear >&2

echo result is: "$result"
```
