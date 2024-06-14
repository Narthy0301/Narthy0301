# Bandit walkthrough log [7 -> 8]

- Login

```
ssh bandit7@bandit.labs.overthewire.org -p 2220
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

- Level Goal

The password for the next level is stored in the file **data.txt** next to the word **millionth**

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/c33588a8-99ab-4bf3-8f0e-8d34688aa760)

We can find "data.txt"file with "ls"command. Let's check it out

```
vi data.txt
/millionth
```

![3](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/49c64643-5e42-4fc5-9b07-b83c8a7fb8fa)

Now we can find a lot of codes. But by entering /millionsth, we can find the data we need.

We can exit by entering :q

```
:q - exit txt file
:w - saving txt file
```

Now we can see a password!

```
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

