# Lab Report 4 - Vim
## Step 4: Log into ieng6
![Image](lab4(1).png)

Keys pressed: I typed the bash ```history``` command and pressed ```<enter>```. Then I used the ```<Ctrl-R>``` command, typing in ```"ss"``` until my entire ```ieng6``` account appeared then pressed ```<enter>``` to log in. 


## Step 5: Clone fork of the repository from Github (with ```SSH``` URL)
![Image](lab4(fork).png)

Keys pressed: I navigated to GitHub and pressed the ```Fork``` button on the top-right followed by the green ```Create fork``` button to fork the ```lab7``` repository. Next, I pressed the big green ```< > Code``` button and went to the ```SSH``` tab. Using ```<Command-C>```, I copied the ```SSH``` link. 

![Image](lab4(2).png)

Keys pressed: I returned to my terminal and typed the ```git clone``` command followed by ```<Space>``` and ```<Command-V>``` to paste the ```SSH``` fork URL. Then I pressed ```<enter>``` to clone the ```lab7``` repository.

## Step 6: Run the tests, demonstrating that they fail
![Image](lab4(3).png)

Keys pressed: I am currently in the ```./``` directory of my terminal. I used the ```cd``` command followed by ```<space>``` and ```"lab7"``` to enter the ```lab7``` directory. Then I typed ```bash test.sh``` followed by ```<enter>``` to run the ```shell``` scripts that execute the test cases in ```ListExamplesTests.java```. 

## Step 7: Edit the code file to fix the failing test
![Image](lab4(4).png)

Keys pressed: I first use the ```vim``` command followed by ```<Space>``` ```"ListExamples.java"``` and ```<enter>``` to open the ```ListExamples.java``` file with ```vim```. I then use the ```"</>"``` command followed by ```"index"``` to search for occurrences of the word ```"index"```. I use the sequence of ```<n><n><n><n><n><n><n><n><n><n>``` to navigate down the instances of ```"index"``` until I find the location of the error. Next, I use the ```<Ctrl-A>``` to navigate my cursor to the end of ```"index1"```, where the error is located. Next, I use the ```cl``` command to enter ```INSERT``` mode and delete the ```"1"``` on the left of the cursor. I then enter ```'2'``` to fix the bug in the code and use ```<Esc>``` to exit ```INSERT``` mode and return to normal mode. ```:wq``` is used to save the changes made to the ```ListExamples.java``` file and exit ```vim```. 

## Step 8: Run the tests, demonstrating they succeed
![Image](lab4(5).png)

Keys pressed: Similar to step 6, I typed ```bash test.sh``` followed by ```<enter>``` to run the tests. 

## Step 9: Commit and push to GitHub











