You can have multiple github accounts with:

https://superuser.com/questions/366649/ssh-config-same-host-but-different-keys-and-usernames

```ssh
Host github.com
   User git
   HostName github.com
   IdentityFile ~/.ssh/id_rsa_pro
   IdentitiesOnly yes
Host github-yazgoo
   User git
   HostName github.com
   IdentityFile ~/.ssh/id_rsa
   IdentitiesOnly yes
```

Then just add to personal repo .git/config:

```
[url "git@github-yazgoo:"]
    insteadOf = git@github.com:
```
