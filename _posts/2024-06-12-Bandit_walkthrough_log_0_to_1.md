# Bandit walkthrough log [0->1]

- How to access to Bandit

  Among the war games provided by Over The Wire called Bandit, Bandit is made to learn the functions of Linux. For system security, you need to know how to handle Linux skillfully, and I would like to learn about Linux through the war game.

  

  ```
  ssh [username]@[servername] -p [portname]
  ```

  

  In the upper left corner of the over the wire website, there is ssh information that can be accessed with Bandit level 0.

  

  The information is 

  SSH Information
  Host: bandit.labs.overthewire.org
  Port: 2220

  

  To access into the machine, I should use a Linux terminal.

  ```
  ssh bandit0@bandit.labs.overthewire.org -p 2220
  ```

  ![2024-06-12 15 30 02](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/d5760e1b-ec61-4028-a740-f89535363820)

The hint of password is on the website

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/aa3bbd26-5520-428d-bca0-35f9c9c1f776)

 After you typed right password you can logged into the machine

**To go to the level 0 -> level 1**

 To go from level 0 to level 1, the following commands must be used

```
ls -> This command will show list of files.
cat [filename] -> This command reads files
```

![2024-06-12 15 49 16](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/15091d7b-d081-420c-822d-4e33ca448582)

The result is the password for the next level for the "bandit0"

```
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

To connect to next level we should disconnect bandit level 0

You can disconnect with following command

```
exit
```

![3](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/da35dec5-4ffb-408f-8c19-96fa5e89e7e3)

The method of accessing the next level is the same as before.

```
ssh bandit[level]@bandit.labs.overthewire.org -p 2220
```

