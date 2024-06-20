# Bandit walkthrough log [14 -> 15]

- Login

```
ssh bandit14@bandit.labs.overthewire.org -p 2220
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

- Level Goal

The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

```
nc localhost 30000
```

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/f70e1e21-89ab-472f-84a1-64706718325f)

Then submit the password of the current level

```
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/a2b8a4eb-0da2-4e97-8fec-367e140a87a6)

Then we can get a password for the next level !

![3](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/dea5cce4-269a-45df-9109-46f2fb95786a)

```
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

