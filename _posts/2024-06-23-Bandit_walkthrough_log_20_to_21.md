# Bandit walkthrough log [20 -> 21]

- Login

```
ssh bandit20@bandit.labs.overthewire.org -p 2220
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```

- Level Goal

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).