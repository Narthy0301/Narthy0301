# Bandit walkthrough log [1->2]

- Login

  ```
  ssh ssh bandit1@bandit.labs.overthewire.org -p 2220
  ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
  ```

  

- Level Goal

  The password for the next level is stored in a file called **-** located in the home directory

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/2dd34d55-3934-431f-a855-444e35e46cdb)

We can search files with command "ls" and we can find a file named "-"

Unlike before, we can see that the cat command cannot read the file.

In this case we can use 

```
Ctrl + c
```

Which is **used to forcefully terminate a running process**

We have to write down all routes in this case.

```
cat /home/bandit1/-
cat ./-
```

We can use both of command 

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/731f7c7e-d225-4723-a1a2-cc44d08a741b)

The result is a password to the next level  

```
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

