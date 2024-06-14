# Bandit walkthrough log [9 -> 10]

- Login

```
ssh bandit9@bandit.labs.overthewire.org -p 2220
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

- Level Goal

The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

```
strings data.txt | grep =
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/d1af1cf9-076e-4c0f-aaf4-63ce741effb4)

```
strings : print the sequences of printable characters in files(특정 문자열 추출)
grep : A command used to search for a particular pattern in a text file and 	   output its results
```

Now we can see the password ! 

```
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

