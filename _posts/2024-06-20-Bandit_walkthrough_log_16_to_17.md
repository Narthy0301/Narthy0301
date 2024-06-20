# Bandit walkthrough log [16 -> 17]

- Login

```
ssh bandit16@bandit.labs.overthewire.org -p 2220
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```

- The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

We have to 'Port Scan' This is the task of checking the open ports.

```
nc -nv -w 1 -z 127.0.0.1 31000-32000 2>&1 | grep succeeded
```

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/3404c946-bea0-40ef-93b3-307a829236f3)

**-n**: Use numeric-only IP addresses (no DNS resolution).

**-v**: Verbose mode, providing detailed output.

**-w 1**: Set a timeout for connections.(If there is no response within 1 second it will give up on the 	  current port and move to the next.)

**-z**: Port scanning mode, which does not send any data.

**2>&1 | grep succeeded**: It only shows the results with the word "succeeded".

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/0da65bc7-3aee-459f-8799-6a7b48cb9655)

We can check connectable ports.

Now we will find a port within these ports that will communicate with ssl.

```
openssl s_client -connect localhost:[portnumber] -ign_eof
```

In my case, port 31790 was the answer. And submit the current password. Then you can get private key code. 

(openssl コードの後ろに-ign_eofを入力することに遅く気づいて解くのにすごく時間がかかりました、、、まじで大変でした。;ㅁ;)

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/6402b0aa-a40f-40fd-9ac7-5b4c1b3fe00f)

Now, we are gonna make temporary directory named  'bandit16_temp' and copy this code

```
mkdir /tmp/bandit16_temp
```

After move to  /tmp/bandit16_temp, we are gonna make sshkey file

```
vi sshkey -> and paste the private code 
```

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/50958200-fb28-4a41-a1da-7a7fd668e4b9)

And make ssh connection with

```
ssh -p 2220 bandit17@bandit.labs.overthewire.org -i sshkey -> enter 'yes'
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/9db8568d-45ba-43c6-bc37-f0e924c78b75)

But, if you denied like this,

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/551af0a2-fe70-4a7a-946d-747137e3706d)

We need to set the permission of the file to '400' with the chmod command.

```
chmod 400 sshkey
```

Change permission and try it again and then,

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/10e1c5f8-33bd-49dd-96b1-d54f5ec9a5fe)

We can check the password of the current account with the following command.
Now we have the password for bandit17!

```
cat /etc/bandit_pass/bandit17
```

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/0b540ff9-d2bd-4075-ab70-ca1cba9ff321)

```
EReVavePLFHtFlFsjn3hyzMlvSuSAcRD
```

