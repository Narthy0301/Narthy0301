# Bandit walkthrough log [4 -> 5]

- Login

  ```
  ssh bandit4@bandit.labs.overthewire.org -p 2220
  2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
  ```

- Level Goal

  The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

First of all, we can find " inhere " directory and files inside of the directory

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/bb39574d-402e-41e4-ad51-49c9ca8f83e7)

We can check all the files, but we can use the file command because it is not efficient.

```
file ./*
file : The file command is a tool used to determine the type of file
./* : Use target all items in the current directory.
```

![3](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/716a21c5-3e21-491f-aa3e-ba9e6059f038)

Now we can see that -file07 is a ASCII text file. 

```
cat ./-file07
```

The result is a password to the next level

```
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

