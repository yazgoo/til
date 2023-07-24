# jq 

jq can also be used to generate json, it takes care of escaping all special json chars:

```bash
jq -n --arg body "$body" '{body: $body}'
```
