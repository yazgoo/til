## fixing authoring issues 

https://www.git-tower.com/learn/git/faq/change-author-name-email/

## git please

```gitconfig
[alias]
	please = push --force-with-lease
```

## cannot lock ref

if you get cannot lock ref when trying to pull

```
error: cannot lock ref 'refs/remotes/origin/test/albah': 'refs/remotes/origin/test' exists; cannot create 'refs/remotes/origin/test/albah'
 ! [new branch]          test/albah                                                         -> origin/test/albah  (unable to update local ref)
```

 you can fix it with


```
git fetch --prune ; git gc --aggressive
```
