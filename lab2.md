# Lab Report 2 - Servers and SSH Keys
## Part 1
![Image](chatservercode.png)
### Using ```/add-message```
![Image](chatserver(1).png)
In this example, the ```handleRequest``` method is called and takes the user input URI("100.116.44.247:4899/add-message?s=Hello&user=jpolitz") as the argument. The ```handleRequest``` method checks the path of the URI. Since the URI contains ```/add-messages ``` the method dissects the query key-value pair, assigning the words after ```?s=``` to ```String message``` and the words after ```&user=``` to ```String user```. The ```chatLog``` string appended with ```user + ": " + message + "\n"``` and returned.   



