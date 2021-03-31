# big query

## eval

you do an eval with `EXECUTE IMMEDIATE`
https://towardsdatascience.com/how-to-use-dynamic-sql-in-bigquery-8c04dcc0f0de

can't be used to have a dynamic view though

## bq command on archlinux

somehow bq command is not installed with AUR's google-cloud-sdk,
it can be accessed via

~/.cache/paru/clone/google-cloud-sdk/src/google-cloud-sdk/bin/bq 

## selecting nested structs, adding derived fields

lets say we have:

```json
things: [
         {
         a: 42,
         field: 2
         },

         {
         a: 43,
         field: 3
         },
         ]
```

we can run:

```sql
ARRAY(SELECT as struct thing.*, thing.field * 2 as field_time_2 from unnest(things) as thing) as things
```
which will output:

```json
things: [
         {
         a: 42,
         field: 2
         field_time_2: 4
         },

         {
         a: 43,
         field: 3
         field_time_2: 6
         },
         ]
```

