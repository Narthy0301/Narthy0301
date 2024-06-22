# Bandit walkthrough log [17 -> 18]

- Login

```
ssh bandit17@bandit.labs.overthewire.org -p 2220
EReVavePLFHtFlFsjn3hyzMlvSuSAcRD
```

- Level Goal

There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**

Simply, comparing the differences between the two files. It called 'Binary Diffing'

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/b216288b-0fd3-4a00-bf72-c62537742395)

We can compare two different files with 'diff' command

```
diff passwords.new passwords.old
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/67098ab7-f3bb-41ec-8d91-2c1a3cc70c30)

 It means that the [ x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO ] part of file password.new and the [FtePUTiLiwPzjIFw2T7o57oBS4zUvPpg] part of file password.old are different.

 In other words, we can see that the change point of file password.new is the password.
Now we have a password to go to the next level!

```
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```

