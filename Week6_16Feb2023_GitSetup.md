## Setup Git

Configure ``git`` on your local machine.

1. Configure your identify.
From the command prompt:

```
git config --global user.name "First Name Last Name""
git config --global user.email "firstlast@example.com"
git config --global core.editor nano
git config --global init.defaultBranch main
```

2. Check your settings:

```
git config --list
```

Read more ``git`` documentation here:
[https://git-scm.com/](https://git-scm.com/)


## Use Git

1. Added or modify files to your repo
2. Track changes with:

	```.
	git add .
	```

3. Commit changes and add message

	```
	git commit -m "add message in quotes"
	```

4. Push changes to remote repo with:

	```
	git push origin main
	```

