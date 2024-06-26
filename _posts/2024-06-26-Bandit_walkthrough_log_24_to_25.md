# Bandit walkthrough log [24 -> 25]

- Login

```
ssh bandit24@bandit.labs.overthewire.org -p 2220
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
```

- Level Goal

 Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

- Solution

  Make a temporary directory in /tmp

```
mkdir /tmp/bandit24_temp
```

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/63f33e1d-ffe5-4887-9d78-0df6a1c3b2c4)

and make a script file with

```
vi temp.sh
```

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/d22ad0d5-2ddc-413f-9c40-df1c3f588538)

```
#!/bin/bash

for i in {j0000..9999}
do
	echo "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i"
done
```

and set permission to 

```
chmod u+x temp.sh
```

then run the file and connect to 30002 port as level goal says !

```
./temp.sh | nc localhost 30002 | grep -v "Wrong"
```

![1](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/f4932c99-8328-4f78-b44c-bb47c4647558)

This code means that 

run temp.sh, and this output goes to 'nc localhost 30002' and then the output of 'nc' command goes to "grep" which means outputs the results except for the word "Wrong".

Then we can see a password for the next level !

```
iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
```

