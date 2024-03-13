# Lab Report 5 - Putting it All Together
## Part 1 - Debugging Scenario
---
### List-Example-Grader HELP!!!
### Student: Keroppi 
Hello! I am working on my ```list-examples-grader``` and ran into a problem. I have 3 test cases in my ```TestListExamples.java``` file. However, when I run ```bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected```, which I got from the week 6 lab sample submissions, the score is always out of 1 instead of 3. I think this might have something to do with my ```JUnit``` test in the ```TestListExamples.java``` or how I cropped the ```JUnit``` results in my ```grade.sh``` script, but nothing I tried is fixing the bug. What is wrong with my code? I included the output symptom below. 

![Image](lab5(1).png)

---

### Re: List-Example-Grader HELP!!!
### TA: Badtz-Maru
Hi! Although it is hard to tell from your screenshot, redirecting the ```JUnit``` output to another file when you run the ```java``` command is a useful tool to help you debug. Then, you will be able to see if the tests ran or if something went wrong.

In the ```list-examples-grader``` we made in class, we used the ```java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > junit-output.txt``` command to redirect the ```JUnit``` output to a file called ```junit-output.txt``` in the ```/home/list-examples-grader/grading-area``` directory. See if you have this command or add it and check the contents in the file to gain more insight into the bug in your code. 

---

### Re:Re: List-Example-Grader HELP!!!
### Student: Keroppi 
Thank you for the suggestion! I found the ```junit-output.txt``` file in the ```/home/list-examples-grader/grading-area``` directory. The file shows:
![Image](lab5(2).png)
Now I know that the ```TestListExamples.java``` ```JUnit``` test file is not found. However, as you can see in the sidebar, I have the ```TestListExamples.java``` there. Why is it not working?

---

### Re:Re:Re: List-Example-Grader HELP!!!
### TA: Badtz-Maru

I noticed that your ```TestListExamples.java``` file is in the ```/home/list-examples-grader``` directory while your ```lib``` directory is in the  ```/home/list-examples-grader/grading-area``` directory. Remember, if a class path is not provided, the ```java TestListExamples``` command only searches the current working directory for the ```TestListExamples.java``` file. Make sure your ```TestListExamples.java``` is in the same directory as the one you run the ```java``` command in your ```grade.sh``` from.

---

### Re:Re:Re:Re: List-Example-Grader HELP!!!
### Student: Keroppi 
Thank you so much! I realized that I was running the ```java -cp $CPATH org.junit.runner.JUnitCore -cp TestListExamples.java > junit-output.txt``` command in my ```grade.sh``` script from the ```/home/list-examples-grader/grading-area``` directory, while my ```TestListExamples.java``` file is in the parent directory of ```/home/list-examples-grader```. Therefore, the mismatch between my current working directory and the directory of the ```TestListExamples.java``` file caused it not to be found by the ```java``` command. I fixed this error by using the ```cp TestListExamples.java grading-area``` command in my ```grade.sh``` file to copy the ```TestListExamples.java``` file into the ```/home/list-examples-grader/grading-area``` directory before I ran the ```java``` command. 

#### Now the content of ```junit-output.txt``` shows that the tests passed and ran:

![Image](lab5(3).png)

#### And the score is out of 3:

![Image](lab5(4).png)

---

## Set-up
### File & directory structure
```
|- list-examples-grader
    |- lib
        |- hamcrest-core-1.3.jar
        |- junit-4.13.2.jar
    |- student-submission
        |- ListExamples.java
    |- grade.sh 
    |- TestListExamples.java
```
### ```grade.sh``` before fixing the bug

![Image](lab5(5).png)

### ```grade.sh``` after fixing the bug

![Image](lab5(6).png)

### ```TestListExamples.java``` Set-up (no changes were made)
![Image](lab5(8).png)


### Full command line ran to trigger the bug
The bug is triggered by running ```bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected``` in the terminal with a link to a git repository.

The git link ```https://github.com/ucsd-cse15l-f22/list-methods-corrected``` is from the week 6 lab sample submissions and is supposed to pass all the tests.

![Image](lab5(1).png)

### Description of what to edit to fix the bug
The bug came from a mismatch between the classpath ```CPATH``` the ```java``` command is run with and the location of the ```TestListExamples.java``` file that contains the ```JUnit``` tests. The ```CPATH``` is ```.:./lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar:``` which only searches the current working directory of ```/home/list-examples-grader/grading-area``` while the ```TestListExamples.java``` file is in the parent directory (```/home/list-examples-grader/```). Therefore, it could not be found.

A solution to this issue is to use the ```cp TestListExamples.java grading-area``` command in ```grade.sh``` to copy the ```TestListExamples.java``` file into the ```/home/list-examples-grader/grading-area``` directory so it can be found in the location indicated by the classpath ```CPATH```.

## Part 2 - Reflection

In the second half of this quarter, I learned more about ```bash``` and ```vim```. I thought it is really cool that I can make an auto grader using ```bash``` and output the score depending on the number of ```JUnit``` tests the submission code passed. The ability to redirect standard output and standard error is always very useful (as seen in my debugging scenario). I am still getting used to the ```vim``` commands, but I really like how easy it makes editing files from the command line. In addition, I can now use ```git``` more fluently and ```add```, ```commit```, and ```push``` my changes to be reflected on the commit log. 








