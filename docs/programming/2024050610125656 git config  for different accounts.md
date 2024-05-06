# Git config for different accounts
❯ cat ~/.gitconfig

```
[includeIf "gitdir:~/workspace/jobname/"]
	path = .gitconfig.work
```


❯ cat ~/.gitconfig.work
```
[user]
	name = "Lilit Smotrova"
	email = "lilit.smotrova@jobname.com"
```

