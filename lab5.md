# Lab Report 5 - Putting it All Together
## Step 1 - Debugging Scenario
---
### List-Example-Grader HELP!!!
### Student: Keroppi 
Hello! I am working on my ```List-Examples-Grader``` and ran into a problem. I have 3 test cases in my ```TestListExamples.java``` file. However, when I run ```bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected```, which I got from the week 6 lab sample submissions, the score is always out of 1 instead of 3. I think this might have something to do with my ```JUnit``` test in the ```TestListExamples.java``` or how I cropped the JUnit results in my ```grade.sh``` script, but nothing I tried is fixing the bug. What is wrong with my code? I included the output symptom below. 

![Image](lab5(1).png)

---

### Re: List-Example-Grader HELP!!!
### TA: Badtz-Maru
Hi! Although it is hard to tell from your screenshot, redirecting the JUnit output to another file is a useful tool to help you debug. Then, you will be able to see if the tests passed or if something went wrong.

In the ```List-Examples-Grader``` we made in class, we used the ```java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > junit-output.txt``` command to redirect the ```JUnit``` output to a file called ```junit-output.txt``` in the ```/home/list-examples-grader/grading-area``` directory. See if you have this command or add it and check the contents in the file to gain more insight into the bug in your code. 

---

### Re:Re: List-Example-Grader HELP!!!
### Student: Keroppi 
Thank you for the suggestion! I found the ```junit-output.txt``` file in the ```list-examples-grader/grading-area``` directory. The file shows:
![Image](lab5(2).png)
Now I know that the ```TestListExamples.java``` ```JUnit``` test file is not found. However, as you can see in the sidebar, I have the ```TestListExamples.java``` there. Why is it not working?

---

### Re:Re:Re: List-Example-Grader HELP!!!
### TA: Badtz-Maru

I noticed that your ```TestListExamples.java``` file is in the ```/home/list-examples-grader``` directory while your ```lib``` directory is in the  ```/home/list-examples-grader/grading-area``` directory. Make sure the path of the ```CPATH``` in your ```grade.sh``` matches the location of the ```TestListExamples.java``` file so your test file can be found and the ```JUnit``` tests can run.

---

### Re:Re:Re:Re: List-Example-Grader HELP!!!
### Student: Keroppi 
Thank you so much! I checked the ```CPATH``` in my ```grade.sh``` script which I am running from the ```/home/list-examples-grader/grading-area``` directory and realized that the ```CPATH``` I provided (```.:./lib/hamcrest-core-1.3.jar:../lib/junit-4.13.2.jar:```) is only searching the current working directory ```/home/list-examples-grader/grading-area``` for the ```TestListExamples.java``` file. However, my ```TestListExamples.java``` file is stored in the parent directory. Therefore, it could not be found. I fixed this error by using the ```cp TestListExamples.java grading-area``` command in my ```grade.sh``` file to copy the ```TestListExamples.java``` file into the ```grading-area``` directory before I ran the ```java``` command. 

#### Now the content of ```junit-output.txt``` shows that the tests passed and ran:

![Image](lab5(3).png)

#### And the score is out of 3:

![Image](lab5(4).png)

---

## Set-up
### File & directory structure
```
    |- grading-area 
		|- lib
        	|- hamcrest-core-1.3.jar
        	|- junit-4.13.2.jar
        |- compile.txt
        |- IsMoon.class
		|- junit-output.txt
		|- ListExamples.class
		|- ListExamples.java
		|- StringChecker.class
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










