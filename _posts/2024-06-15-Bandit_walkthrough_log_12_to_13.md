# Bandit walkthrough log [12 -> 13]

- Login

```
ssh bandit12@bandit.labs.overthewire.org -p 2220
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```

- Level Goal

The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

Before solve this problem we better make temporary file on tmp directory .

```
mkdir /tmp/temp
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/361e6225-7949-4085-822c-26aef502d04b)

and copy data.txt file to temporary directory.

```
cp data.txt /tmp/temp
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/58af6d1d-bb49-4fc7-8c30-8530577e121d)

We need to reverse this file because it is a hexdump file into temp

```
xxd -r data.txt > temp
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/7de37738-47ea-432c-8bfa-162cd66fc575)

Now let's find out what file this is.

```
file temp
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/4eaaffb4-d667-4b39-a67b-786d10edbeac)

Now we can see 'temp' is compressed by 'gzip'

To decompress this file, the extension must be changed to 'gz'.

```
mv temp temp.gz
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/78704242-e10a-4aac-b0c3-01e59ca57bf6)

Now we can decompress and what result is

```
gunzip temp.gz
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/4d8323b9-86f4-4634-892a-7c586f489f2a)

```
file temp
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/979d3a23-ed57-445f-90bd-7ea737ffef83)

Now we can see 'temp' is compressed by 'bzip2'

To decompress this file, the extension must be changed to 'bz2'.

```
mv temp temp.bz2
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/b2526726-6891-4f83-b14e-2ac723d1a8c4)

Let's find out what file this is.

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/120af9b5-84f6-46b4-a1b6-ebb87eca11cb)

```
bzip2 -d temp.bz2
```

Now we can decompress and what result is

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/a70ac018-c108-4b0b-b37e-b032f4bf2717)

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/d261f227-1aa4-4125-a43c-c2c0bb51bac7)

We can see 'temp' is compressed by 'gzip' again.

```
mv temp temp.gz
gunzip temp.gz
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/2f937cfe-a58a-43b3-8179-5b9e1837fd30)

We can see 'temp' is compressed by 'POSIX'

```
mv temp temp.tar
tar -xf temp.tar
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/8a6565ba-bca8-4dd8-882d-44b8d9bd5c46)

Now we can see the result is data5.bin and data5.bin is compressed by POSIX again.

```
mv data5.bin data5.tar
tar -xf temp.tar
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/ac47fccd-819b-43ee-9f37-0224019d5898)

Now we can see the result is data6.bin and it is compressed by bzip2

```
mv data6.bin data6.bz2
bzip2 -d data6.bz2
```

The result is 'data6' and it's compressed by POSIX.

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/30a179b1-1bf1-409a-a99b-dba0046cc0dc)

```
mv data6 data6.tar
tar -xf data6.tar
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/7c4317dc-c1f8-4490-a1c4-86e3c9ad3dfb)

We can find 'data8.bin' . data8.bin is compressed by gzip

```
mv data8.bin data8.gz
gunzip data8.gz
```

![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/9589022c-76ba-4cb2-9904-93aca40824cf)

The result is ASCII text file !

Now we can see the password !

```
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```

It was pretty boring process...,