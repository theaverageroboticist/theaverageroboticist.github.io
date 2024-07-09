+++
title = 'Git Commands'
date = 2024-05-30T18:24:33+02:00
draft = true
+++

## Configuring Git

### Identity

Setting up user name and email address is the first thing one should, since all the commits will have this information. You can set up the identity either globally with `--global` option or only for a local repo with `--local`.

`git config --global user.name "User Name"`  
`git cofig --global user.email "user@example.com"`

### Having multiple cofig files

If we want to have a personal config and a work config we can tell git to look for config files that are specific for that directory.

```
[includeIf "gitdir:~/home/work/"]
    path =~/home/work/,gitconfig
[includeIf "gitdir:~/home/personal/"]
    path =~/home/personal/,gitconfig
```

Whenever you do something from these directory git will use these config files.

### Default Branch

Whenever you initialize a git repository it will create a beanch with the name **master**, you can change this by `git config --global init.defaultBranch main`.  
Now any new `git init` will create a Branch called main.

### Aliases

We can create aliases for our most used commands in git, set the alias you want like this example `git cofig --global alias.cmt 'commit -m'`.

Now we can commit by using `git cmt "our message"`

When using the `--global` option the config is saved to the `~/.gitconfig` or `~/.config/git/config`.

The same action can be performed with the `--local` option which saves the changes to the current repositories `.git/config`.

You can check all the **config Settings** with `git config --list`.

## Common commands

`git blame <file/ path to file>` get the blame for the whole file  
`git blame -L 1,20 <file/ path to file>` gives the balme only for the specified line range  
`git blame -w -C -C -C -L 1,20 <file/ path to file>` this will ignore the whitespace and detect lines that are moved or copied in the same commit/commits that created the file/ any commit at all.

`git log <file>` to view the log for a file  
`git log -S <something to search> -p` search for a chage in the log, a grep like feature for the log.

`git reflog` will give out a reference log for each action that has been made using git 

`git diff` will give the changes made to file line by line  
`git diff --word-diff` will give the changes made word by word.



### References

[Git](https://git-scm.com/book/en/v2/)
