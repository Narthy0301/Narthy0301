# Bandit walkthrough log [15 -> 16]

- Login

```
ssh bandit15@bandit.labs.overthewire.org -p 2220
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

- Level Goal

The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

```
openssl s_client -connect localhost:30001
```

*localhost means 'myself'

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/3b62dbe0-26e6-44ea-8d2e-f9d047528a2e)

Now we can see openssl was connected

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/d8cb5968-3379-4177-8c99-b9a8b1d08d7d)

(We can check connected with TLS)

```
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

![3](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/f7a6ef0e-552b-421b-a3ce-dc8c7035e179)

```
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```

Now we can see a password for the next level !