# Bandit walkthrough log [11 -> 12]

- Login

```
ssh bandit11@bandit.labs.overthewire.org -p 2220
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

- Level Goal

The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

This problem is encrypted by the rot13 technique.

*It is an encryption technique that moves alphabetic characters by 13 characters.

There are two solutions to this problem.

```
tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt
```

and 

```
https://rot13.com/
```

putting an encrypted string on the above site.

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/9783adcf-de64-42e4-9a0c-cc789b609dc3)

Now we can see the password !

```
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```

