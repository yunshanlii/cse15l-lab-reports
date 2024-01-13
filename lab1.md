# Lab Report 1 - Remote Acess and FileSystem
## ** cd command**
> The ```cd``` command-line command is used to change the working directory
1. no argument
   ```
   [user@sahara ~/lecture1/messages]$ cd
   [user@sahara ~]$ 
   ```
   When used with no argument, the ```cd``` command exits all current directories and returns to the ```/home``` directory.
2. path to a directory as an argument
   ```
   [user@sahara ~]$ cd lecture1
   [user@sahara ~/lecture1]$ cd messages
   [user@sahara ~/lecture1/messages]$ 
   ```
   When used with a path to a directory as an argument, the ```cd``` command changes the current directory to the one specified in the argument. However, the argument directory must be directly within the current working directory, or a "no such file or directory" error will occur. 
3. path to a file as an argument
   ```
   [[user@sahara ~]$ cd lecture1/messages/
   [user@sahara ~/lecture1/messages]$ cd en-us.txt
   bash: cd: en-us.txt: Not a directory
   ```
   When  used with a path to a file as an argument, the ```cd``` command will result in a "Not a directory" error as the ```cd``` command can not make a file the current working directory.

## **ls command**
> The ```ls``` command-line command is used to list all the files in the working directory
1. no argument
   ```
   [user@sahara ~]$ ls
   lecture1
   [user@sahara ~]$ cd lecture1
   [user@sahara ~/lecture1]$ ls
   Hello.class  Hello.java  messages  README
   ```
   When used with no argument, the ```ls``` command prints out the names of all the directories and files in the current working directory.
2. path to a directory as an argument
   ```
   [user@sahara ~]$ ls lecture1
   Hello.class  Hello.java  messages  README
   [user@sahara ~/lecture1]$ ls messages
   en-us.txt  es-mx.txt  ko-kr.txt  zh-cn.txt
   ```
   When used with a path to a directory as an argument, the ```ls``` command prints out the names of all the directories (in blue) and files in the directory specified in the argument. However, the argument directory must be directly within the current working directory to avoid error. 
3. path to a file as an argument
    ```
   [user@sahara ~/lecture1/messages]$ ls en-us.txt
   en-us.txt
   ```
   When used with a path to a file as an argument, the ```ls``` command will output the name of the file. 
     
## **cat command**
> The ```cat``` command-line command stands for concatenate and can be used to concatenate the contents of multiple files and print the contents of a single file.  
1. no argument
   ```
   [user@sahara ~]$ cat
   hello world!
   hello world!
   ^C
    ```
   When used with no argument, the ```cat``` command will prompt for user input and output the input over and over until ```Ctrl+C``` is pressed to stop the cycle.   
2. path to a directory as an argument
   ```
   [user@sahara ~]$ cat lecture1
   cat: lecture1: Is a directory
    ```
   When used with a directory as an argument, the ```cat``` command will display that the argument directory is a directory; therefore, the ```cat``` command can not concatenate the directory.
3. path to a file as an argument
   ```
   #single txt file as argument
   [user@sahara ~/lecture1/messages]$ cat en-us.txt
   Hello World!
     ```
   ```
   #multiple txt file as argument
   [user@sahara ~/lecture1/messages]$ cat en-us.txt es-mx.txt zh-cn.txt
   Hello World!
   ¡Hola Mundo!
   你好世界
     ```
   ```
   [user@sahara ~/lecture1]$ cat Hello.java
   import java.io.IOException;
   import java.nio.charset.StandardCharsets;
   import java.nio.file.Files;
   import java.nio.file.Path;

   public class Hello {
     public static void main(String[] args) throws IOException {
       String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
       System.out.println(content);
     }
   ```
   

   
     

     
