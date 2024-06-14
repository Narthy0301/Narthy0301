# Bandit walkthrough log [5 -> 6]

- Login

  ```
  ssh bandit5@bandit.labs.overthewire.org -p 2220
  4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
  ```

- Level Goal

  The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

  - human-readable
  - 1033 bytes in size
  - not executable

  We need to find a file that meets three conditions in a hidden directory. We can use "find" command which is files.

  ```
  find ./ -type f -size 1033c ! -executable
  ```

The following options are required when using the find command.



-type f , -size , -executable(with !)



The -type f option is used to search for "regular files" in the file system, which means that the search is conducted only on files, not directories.

The -size option is used to search for files based on the size of the file. c is used to specify the size unit

The -executable option is used when searching for executable files. and ! means NOT. In other words, look for the non-executable file.



![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/f0578aea-96d8-4d27-ab1b-dc7bc8b45a30)

Now we can see the password !

```
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```


