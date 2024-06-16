# Bandit walkthrough log [10 -> 11]

- Login

```
ssh bandit10@bandit.labs.overthewire.org -p 2220
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

- Level Goal

The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

You can use the base64 command to decode the data encoded in base64, using the -d or --decode option.

```
base64 data.txt -d
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/72f59a27-a49a-4951-9e0c-beb899eb6faf)

Now we can see the password !

```
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

