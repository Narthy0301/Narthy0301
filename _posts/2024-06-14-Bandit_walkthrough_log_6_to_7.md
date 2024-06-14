# Bandit walkthrough log [6 -> 7]

- Login

```
ssh bandit6@bandit.labs.overthewire.org -p 2220
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

- Level Goal

The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

This level is similar to level 6.

```
find / -user bandit7 -group bandit6 -size 33c 2> /dev/null
cat /var/lib/dpkg/info/bandit7.password
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/f24d0383-bfff-4fae-9282-cad915578031) 

*2> /dev/null means 2> /dev/null means to delete the error messages.



Now we can see the password for next level !

```
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

