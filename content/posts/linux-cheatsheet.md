+++
title = 'Linux Cheatsheet'
date = 2024-04-09T21:43:58+02:00
draft = false
description= "Linux commands for begineers"
tags= ["linux", "cheatsheet", "shell"]
aliases= ["migrate-from-jekyl"]
categories= ["linux", "cli"]
series= ["Linux Begineers"]
ShowToc= true
TocOpen= true
+++

Use the `man <Command>` to get the manual page for the commands Ex,
> man rm

### File Management

| Command                              | Description                                              |
| ----                                 | ---                                                      |
| `ls -la`                             | *List all files/folders* present in the directory        |
| `pwd`                                | Obtain the path of *current working directory*           |
| `cd <directory name>`                | Change to the directory name                             |
| `touch  <filename.extension>`        | *Create a file*                                          |
| `mkdir -p parentdirectory/directory` | *Create a folder* with all parent directories            |
| `rm <filename>`                      | *Remove a file*                                          |
| `rm -r <directory>`                  | *Remove a directory*, `-r` removes the files recursively |

### Searching

| Command                                                   | Description                                                                                   |
| ----                                                      | ---                                                                                           |
| `grep "<something>" filename`                             | Find "something" the file "filename"                                                          |
| `grep -i "<something>" filename`                          | Making it case insensitive with `-i`                                                          |
| `grep -ro <something> <path>/`                            | Search for something in path `-ro` makes it recursive showing only matched pairs              |
| `find /path/to/folder/ -name *nameOrportion of the file*` | Find the file in the given path use `type f` for only files and `type d` for only directories |
| `locate -i filename`                                      | `-i` to ignore case                                                                           |

### Using Multiple Commands

Using semicolon between commands `ls ; whoami ; pwd` will execute all the commands one by one.  
The next commad will be executed even if the previous ones fail.

Using the `&` operator will execute the next commad if only the previous one suceeds.  
`mkdir folder && cd folder` will create and cd to the folder but the other way arround will  
not work since there will be no directory to change.

Using the `||` operator will execute the next commad if the previous one fails.
`cd folder || mkdir folder` if there id no folder then this commad will make a new one.

Using the `|` piping operator will redirect the first commands output to the second one.
`ls -la | grep -i <something>` the grep commad will Search for something from the output
of ls.





