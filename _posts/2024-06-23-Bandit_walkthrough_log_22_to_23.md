# Bandit walkthrough log [22 -> 23]

- Login

```
ssh bandit22@bandit.labs.overthewire.org -p 2220
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
```

- Level Goal

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

- Solution

Let's go to /etc/cron.d/ and check bandit23.sh as we did last time

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/9fd466d0-09ec-46e7-b86a-22a135a7d2e5)

And enter the command 

```
cat cronjob_bandit23
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/98ff4880-9311-4331-a0a1-389ab4cf1aab)

Then we can check the shell.

![3](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/c7312832-4e7f-45dc-8cef-61348c5c73bd)

 To explain little bit, 'myname' and 'mytarget' are variable.

 This codes mean 'myname' (include 'whoami') goes to 'mytarget'. And it saves in to /tmp/$mytarget. So we should check the contents of /tmp/$mytarget. But this file is going to run with bandit23 permission so we have to modify some codes.

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/2016aaad-b54f-4db3-86bc-9a2802f8361c)

```
#!/bin/bash

myname='bandit23'
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo $mytarget
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/1713b883-5aac-4c24-bd2c-46175719eca0)

Save this modified shell into /tmp

![3](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/22f4e265-3ba5-41a0-9dfa-bb4ee2aa54da)

```
chmod u+x shell.sh
./shell.sh
```

**u**: Refers to the user, which means the owner of the file.

**+x**: Adds the execute permission, i.e., grants execute rights.
 Now we can know '8ca319486bfbbc3663ea0fbe81326349' is stored in $mytarget.

![4](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/b26515ec-0d69-4fd4-ad87-5e45cb8186fb)

Now we got a password for the next level !

```
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
```

