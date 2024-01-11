# Lab Report 1 - Remote Acess and FileSystem
## **cd command**
> The cd command-line command is used to change the working directory
1. no argument
   ```
   [user@sahara ~/lecture1/messages]$ cd
   [user@sahara ~]$ 
   ```
   When used with no argument, the cd command exits all current directories and returns to the /home directory.
2. path to a directory as an argument
   ```
   [user@sahara ~]$ cd lecture1
   [user@sahara ~/lecture1]$ cd messages
   [user@sahara ~/lecture1/messages]$ 
   ```
   When used with a path to a directory as an argument, the cd command changes the current directory to the one specified in the argument. However, the argument directory must be directly within the current working directory, or a "no such file or directory" error will occur. 
4. path to a file as an argument
   ```
   [[user@sahara ~]$ cd lecture1/messages/
   [user@sahara ~/lecture1/messages]$ cd en-us.txt
   bash: cd: en-us.txt: Not a directory
   ```
   When  used with a path to a file as an argument, the cd command will result in an "Not a directory" error as the cd command can not make a file the current working directory.

## **ls command**
> The list command-line command is used to list all the files in the working directory
1. no argument
2. path to a directory as an argument
3. path to a file as an argument
     
## **cat command**
> The cat command-line command is used to 
1. no argument
2. path to a directory as an argument
3. path to a file as an argument
     

     
