# Bandit walkthrough log [26 -> 27]

- Login

  ```
  Continue from the previous lecture.
  ```

- Level Goal

  Good job getting a shell! Now hurry and grab the password for bandit27!

- Solution

  We can see 'bandit27-do' file with 'ls' command which is run a command as another user.
    Example: ./bandit27-do id

  ![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/ebc468cc-7ef9-48fb-96fa-8c374fbb5fa1)

```
./bandit27-do cat /etc/bandit_pass/bandit27
```

Now we can get a password for the next level easily!

```
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
```

