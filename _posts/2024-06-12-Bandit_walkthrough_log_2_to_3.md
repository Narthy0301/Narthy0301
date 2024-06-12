# Bandit walkthrough log [2->3]

- Login

  ```
  ssh bandit2@bandit.labs.overthewire.org -p 2220
  263JGJPfgU6LtdEvgfWU1XP5yac29mFx
  ```

- Level Goal

  The password for the next level is stored in a file called **spaces in this filename** located in the home directory

  ![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/5f7eda47-1a32-4a1b-8ce8-6fed3fe7cb79)

  We can search files with command “ls” and we can find a file named “spaces in this filename“ 

  However, we can see that it does not read normally when using the cat command.

  We can see that the sentence spaces in this filament is recognized word by word.
  That's why we need to make it understood in one sentence.

  ![2](https://github.com/Narthy0301/Narthy0301.github.io/assets/172380852/b0551d5c-aa27-4f84-9f53-4e28f0853b42)

  By using double quotation marks we can make it in one sentence.

  The result is a password to the next level  

  ```
  MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
  ```

  

