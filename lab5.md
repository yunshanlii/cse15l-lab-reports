# Lab Report 5 - Putting it All Together
## List-Example-Grader HELP!!!
### Student: Keroppi 
Hello! I am working on my ```List-Examples-Grader``` and ran into a problem. I have 3 test cases in my ```TestListExamples.java``` file. However, when I run ```bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected```, which I got from the week 6 lab sample submissions, the score is always out of 1 instead of 3. I think this might have something to do with my JUnit test in the ```TestLisstExamples.java``` or how I cropped the JUnit results in my ```grade.sh``` script, but nothing I tried is fixing the bug. What is wrong with my code? I included the output symptom below. 
![Image](lab5(1).png)

## Re:List-Example-Grader HELP!!!
### TA: Badtz-Maru
Hi! Although it is hard to tell from your screenshot, redirecting the JUnit output to another file is a useful tool to help you debug. Then, you will be able to see if the tests passed or if something went wrong.

In the ```List-Examples-Grader``` we made in class, we used the ```java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > junit-output.txt``` command to redirect the JUnit output to a file called ```junit-output.txt```. See if you have this command or add it and check the contents in the file to gain more insight into the bug in your code. 







