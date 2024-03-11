# Lab Report 5 - Putting it All Together
## List-Example-Grader HELP!!!
### Student: Keroppi 
Hello! I am working on my ```List-Examples-Grader``` and ran into a problem. I have 3 test cases in my ```TestListExamples.java``` file. However, when I run ```bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected```, which I got from the week 6 lab sample submissions, the score is always out of 1 instead of 3. I think this might have something to do with my JUnit test in the ```TestListExamples.java``` or how I cropped the JUnit results in my ```grade.sh``` script, but nothing I tried is fixing the bug. What is wrong with my code? I included the output symptom below. 

![Image](lab5(1).png)

## Re:List-Example-Grader HELP!!!
### TA: Badtz-Maru
Hi! Although it is hard to tell from your screenshot, redirecting the JUnit output to another file is a useful tool to help you debug. Then, you will be able to see if the tests passed or if something went wrong.

In the ```List-Examples-Grader``` we made in class, we used the ```java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > junit-output.txt``` command to redirect the JUnit output to a file called ```junit-output.txt``` in the ```/home/list-examples-grader/grading-area``` directory. See if you have this command or add it and check the contents in the file to gain more insight into the bug in your code. 

## Re:Re:List-Example-Grader HELP!!!
### Student: Keroppi 
Thank you so much! I found the ```junit-output.txt``` file in the ```list-examples-grader/grading-area``` directory. The file shows:
![Image](lab5(2).png)
Now I know that the ```TestListExamples.java``` JUnit test file is not found. However, as you can see in the sidebar, I have the ```TestListExamples.java``` there. Why is it not working?

## Re:Re:Re:List-Example-Grader HELP!!!
### TA: Badtz-Maru

Your ```TestListExamples.java``` file is in the ```/home/list-examples-grader``` directory. Which directory are you running the 


Now that the problem has been identified to be that the ```TestListExamples.java``` file is not found, it is highly likely due to a mismatch in your ```CPATH``` in the ```grade.sh``` script and the actual location of your ```TestListExamples.java``` file. Make sure that your ```CPATH``` matches the location of the ```TestListExamples.java``` file so your test file can be found and the ```JUnit``` tests can be run.

I see in your directory structure that ```TestListExamples.java``` is in the ```list-examples-grader``` directory and outside of the ```list-examples-grader/grading-area``` directory. If your ```CPATH``` in the ```grade.sh``` script is looking for 









