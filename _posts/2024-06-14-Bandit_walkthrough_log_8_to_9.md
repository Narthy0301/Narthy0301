# Bandit walkthrough log [8 -> 9]

- Login

```
ssh bandit8@bandit.labs.overthewire.org -p 2220
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

- Level Goal

The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once.

```
sort data.txt | uniq -u
uniq - report or omit repeated lines
The -u option only outputs unique lines that are not duplicated.
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/84fca6b7-2b3a-4ebc-aaf2-2febef584dee)

Now we can see the password !

```
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

