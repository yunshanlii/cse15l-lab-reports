# Lab Report 4 - Vim
## Step 4: Log into ieng6
![Image](lab4(1).png)

Keys pressed: I typed the bash ```history``` command and pressed ```<enter>```. Then I used the ```<Ctrl-R>``` command, typing in ```"ss"``` until my entire ```ieng6``` account appeared then pressed ```<enter>``` to log in. 


## Step 5: Clone fork of the repository from Github (with ```SSH``` URL)
![Image](lab4(2).png)

Keys pressed: I navigated to GitHub to fork the ```lab7``` repository. I pressed the big green ```< > Code``` button and went to the ```SSH``` tab, copying the link. Then I returned to my terminal and typed the ```git clone``` command followed by ```<Space>``` and ```<Command-V>``` to paste the ```SSH``` fork URL. Then I pressed ```<enter>``` to fork the ```lab7``` repository.

## Step 6: Run the tests, demonstrating that they fail
![Image](lab4(3).png)

Keys pressed: I used the ```cd``` command followed by ```<space>``` and ```"lab7"``` to enter the ```lab7``` directory. Then I typed ```bash test.sh``` followed by ```<enter>``` to run the tests. 

## Step 7: Edit the code file to fix the failing test
![Image](lab4(4).png)

Keys pressed: I first use the ```vim``` command followed by ```<Space>``` ```"ListExamples.java"``` and ```<enter>``` to open the ```ListExamples.java``` file with ```vim```. Then I press ```<up>``` ```<up>``` ```<up>``` ```<up>``` ```<up>``` ```<up>``` to navigate my cursor to the error. Next, I use the ```<Ctrl-A>``` to navigate my cursor to the end of ```"index1"```. Next, I use the ```cl``` command to enter ```INSERT``` mode and delete the ```"1"``` on the right of the cursor. I then enter ```'2'``` to fix the bug it the code and use ```<Ctrl-C>``` to exit ```INSERT``` mode and return to normal mode. ```:wq``` is used to save the changes made to the ```ListExamples.java``` file and exit. 








