# Bandit walkthrough log [13 -> 14]

- Login

```
ssh bandit13@bandit.labs.overthewire.org -p 2220
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```

- Level Goal

The password for the next level is stored in **/etc/bandit_pass/bandit14 and can only be read by user bandit14**. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. **Note:** **localhost** is a hostname that refers to the machine you are working on

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/e4c65fb5-2e37-4df6-88b4-93ca21ae43cb)

After we login, we can find somekind of code named sshkey.private. This is gonna be a hint for next level. 

```
ssh -i sshkey.private bandit14@localhost -p 2220
yes
```

![3](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/50e87517-1a17-4b31-b35f-900fd9fd5476)

*The Secure Shell (SSH) protocol *sets up encrypted connections for remote logins and file transfers between computers*.

Through this command(ssh -i) we can try to connect with ssh(for this connection, we need ssh key code ! This is why we use sshkey.private file)

Then enter "yes" on the terminal

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/722c0329-49ac-45c7-a834-3b3c61272eb3)

Then we are able to login to bandit14@bandit !

According to the discription, there is a password on**/etc/bandit_pass/bandit14**

![5](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/dacd4031-d2e1-4322-ab0b-c7bd5dafe224)

Now we got a password !

```
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

