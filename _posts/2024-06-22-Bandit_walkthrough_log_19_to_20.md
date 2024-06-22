# Bandit walkthrough log [19 -> 20]

- Login

```
ssh bandit19@bandit.labs.overthewire.org -p 2220
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```

- Level Goal

 To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/108079f1-0fb2-488a-938c-3d1eec3efcc8)

 There is a file named 'bandit20-do'. This file is 'setuid', which means execute with the permission of its user or owner. When this file is executed, it means that it can be executed with the permission of bandit20. The description of this file describes the command that can execute this.

For example, we can not read password file of bandit20. Because we do not have permission.

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/a07b11d6-38e7-47e8-8d01-9c2edddcf4a8)

But, if we use 'bandit20-do' file, 

![3](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/9f221f44-9918-4a37-b746-8c53d414f7f9)

It makes us can read the file.

Now we get a password for the next level !

```
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```

