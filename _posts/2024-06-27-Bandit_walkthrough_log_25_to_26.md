# Bandit walkthrough log [25 -> 26]

- Login

  ```
  ssh bandit25@bandit.labs.overthewire.org -p 2220
  iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
  ```

- Level Goal

​	Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

- Solution

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/01415c5b-fdd4-48fe-bf62-e162de9e27a4)

There is a sshkey file so we can try to connect ssh with this private key.

​	![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/65d26717-a8d5-4bdc-a365-c23e7334a117)

Enter 'yes'

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/ae4b9939-9704-404a-92b5-a6425b8b37d0)

But, connection is closed. Let's figure the reason

![3](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/b04ddf9e-f3ec-416b-994a-18c4dd2bf3fa)

```
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0
```

Check the shell of  bandit26. 

It can be seen that the shell script is being executed with the 'more' command.
'more' has a function that makes the script easier to read, and I will try to log in with this command.
It is said that this method can be used in penetration tests or hacking.

The way to use more is to reduce the size of the terminal to a smaller size.
Like this.

![4](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/6a9d5798-29b7-4d63-b5a0-c7c161a41a95)

While using 'more' we can run 'vi' function by press 'v' key.

![5](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/9fc752ee-f735-4f47-b577-d34736c0bd97)

```
:set shell=/bin/bash
```

![6](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/797aff28-349a-4f1e-a53d-78d579c65d3d)

```
:shell
```

![7](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/789c54d7-cc08-4d58-aa49-82e226b2c1af)

then we can login bandit26 !
In this time, I will proceed with the process of moving from bandit26 to bandit27.

