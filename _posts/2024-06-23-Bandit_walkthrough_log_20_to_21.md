# Bandit walkthrough log [20 -> 21]

- Login

```
ssh bandit20@bandit.labs.overthewire.org -p 2220
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```

- Level Goal

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

This time, we will use two terminals.

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/819911be-60fc-4edc-984d-42997e3f48e6)

We can know there is a file named 'suconnect' that can be used when making connection.

Now we are going to open port with 

```
nc -lvnp [port number]
```

**-l**: Operates in server mode, waiting for incoming connections.

**-n**: Uses IP addresses only, without resolving hostnames.

**-v**: Enables verbose output, providing more detailed information.

**-p [port number]**: Listens for connections on port number.![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/1810d4ad-4dbb-4f40-af16-9bba24c93d04)

I'll set the port number to 7777. The port number doesn't matter what number it is in this time.

![3](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/bba774c6-77fe-459f-b3be-2adfbf9f1b26)

```
./suconnect 7777
```

By this command, we can try to make connection with other terminal. 

And submit the current password. Then we can get a password for next level !

```
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```

