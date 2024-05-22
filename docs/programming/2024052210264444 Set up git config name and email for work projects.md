---
tags:
  - gitconfig
---

# Set up git config name and email for work projects

```bash
vim ~/.gitconfig
```

Add lines:

```txt
[includeIf "gitdir:~/workspace"]
	path = .gitconfig.work
```


```bash
vim .gitconfig.work
```

Add lines:
```txt
[user]
	name = "YOUR NAME"
	email = "YOUR WORK EMAIL"
```

