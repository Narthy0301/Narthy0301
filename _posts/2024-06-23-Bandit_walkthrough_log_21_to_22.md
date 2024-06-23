# Bandit walkthrough log [21 -> 22]

- Login

```
ssh bandit21@bandit.labs.overthewire.org -p 2220
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```

- Level Goal

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

- Solution

 This time, we will use cron. Cron is simply a program that allows you to execute instructions on a schedule. Let's check **/etc/cron.d/** 

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/b33f5b8e-cb48-4873-9282-588523428ed5)

 There is a cronjob_bandit22 file. The contents of the file are as follows.

```
cat cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
```

 We can set the cycle differently depending on the location of each star, in the order of minutes-hours-days-months-days. If there are five stars, it will run every minute. 

Simply put, it means running /usr/bin/cronjob_bandit22.sh every minute.

So lets check  /usr/bin/cronjob_bandit22.sh now.

![3](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/615a3a64-27ae-4738-a260-05f88c34fd34)

I think this program is saving something from 

[/etc/bandit_pass/bandit22]  to  [/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv]. 

And I think it will be a password to the next level.

![4](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/2db85dc3-c9c7-46ff-8cee-e9de813b7996)

Now we get a password for the next level !

```
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
```

