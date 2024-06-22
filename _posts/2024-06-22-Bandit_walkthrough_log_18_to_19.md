# Bandit walkthrough log [18 -> 19]

- Login

```
ssh bandit18@bandit.labs.overthewire.org -p 2220
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```

- Level Goal

 The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.

In this level, if you try to connect to bandit18, you will disconnected by server.

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/4668dd0c-a7f4-4268-a93e-9b074f69988c)

But, we can give additional commands when we try ssh connection. For example, 

```
ssh bandit18@bandit.labs.overthewire.org -p 2220 id
```

and then the result will be like this.

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/2da51af4-c20a-47f7-9d78-518403a6a2de)

We can see 'id' information. Using this, we can command the server before it is disconnected.

```
ssh bandit18@bandit.labs.overthewire.org -p 2220 /bin/sh
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/9ef40866-f0dc-49f7-889f-911cff6862db)

We can check we are in bandit18 now with 'pwd' command.

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/7d0600f8-c3cf-4666-8452-264729a62da1)

By 'ls' command, we can check there is a 'readme' file with the password

```
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```

Now we got the code !
