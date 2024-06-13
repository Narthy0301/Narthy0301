# Bandit walkthrough log [3->4]

- Login

  ```
  ssh bandit3@bandit.labs.overthewire.org -p 2220
  MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
  ```

- Level Goal

​	The password for the next level is stored in a hidden file in the **inhere** directory.

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/f8d5c08c-f62e-460a-a013-202d3b8ca051)

We can see that using the ls command does not look up any files.

In this case we should use "option"

```
ls + -al
-l : Print out in detail when listing files.
-a : List all files in the path (including hidden files)
```

![3](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/8c287462-9096-4036-912b-bb5d9e9d67c2)



We can see hidden file named "...Hiding-From-You"

```
cat ...Hiding-From-You
```

![4](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/2e80bf12-8b28-4ca6-bd8d-af34e3a3fc3e)

The result is a password to the next level

```
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```



