# Lab Report 2 - Servers and SSH Keys
## Part 1
![Image](chatservercode.png)
### Using ```/add-message```
![Image](chatserver(1).png)
In this example, the ```handleRequest``` method is called and takes the user input URI("http://100.116.44.247:4899/add-message?s=Hello&user=jpolitz") as the argument. The ```handleRequest``` method checks the path of the URI. Since the URI contains ```/add-messages ``` the method dissects the query key-value pair, assigning the words after ```?s=``` to ```String message``` and the words after ```&user=``` to ```String user```. Thus, ```message``` has the value "Hello" and ```user``` has the value "jpolitz". The ```chatLog``` string gets appended with ```user + ": " + message + "\n"``` and returned. Now, ```chatLog``` has the value "jpolitz: Hello".

![Image](chatserver(2).png)
In this example, the ```handleRequest``` method is called again and takes the user input URI("http://100.116.44.247:4899/add-message?s=How%20are%20you&user=yash") as the argument. The ```handleRequest``` method checks the path of the URI. Since the URI contains ```/add-messages ``` the method dissects the query key-value pair, assigning the words after ```?s=``` to ```String message``` and the words after ```&user=``` to ```String user```. Consequently, ```message``` has the value "How are you" and ```user``` has the value "yash". The ```chatLog``` string gets appended with ```user + ": " + message + "\n"``` and returned. Finally, ```chatLog``` has the value "jpolitz: Hello\nyash: How are you".   

## Part 2
### Absolute path to the private key
![Image](privatekey.png)

### Absolute path to the public key
![Image](publickey.png)

### Login without password
![Image](loginwithoutkey.png)

## Part 3







