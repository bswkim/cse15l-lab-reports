# Lab Report 4 
> Brian Kim, A17462905

This is a resubmission file, and the problem with the first submission was that I did not clone the file with ssh. At first, I tried to remove the folder lab7-lab4demo-briankim, but it did not work due to the permission issue. Therefore, on my github, I deleted the fork and created a new fork named lab7-briankim-lab4. So, for the parts that are changed on the second submission, the name of the repo would be changed. However, I still followed the same exact process, and this is a reminder prevent confusion. I hope this does not cause problems.  

## Log into ieng6 

<img src="lab4login2.png" width="500" height="200">

Keys pressed: ```ssh cs15lsp23nv@ieng6.ucsd.edu <enter>``` Then, ```<Password> <enter>``` to login to the remote cs15lsp account using ssh. 

## Clone your fork of the repository from your Github account

<img src="lab4clone2.png" width="700" height="200">

Keys pressed: ```git clone``` after doing that, I pressed ```<command> + <v>``` which is ```https://github.com/bswkim/lab7-lab4demo-briankim.git <enter>```, the https from my github to copy and paste the repo to the remote account. 

## Run the tests, demonstrating that they fail

<img src="lab4fail.png" width="600" height="200">

First, I accessed the lab7-lab4demo-briankim repo using cd. Keys pressed were: ```cd lab7-lab4demo-briankim <enter>```. And then, I pressed ```bash test.sh <enter>``` to run the bash script inside the lab7-lab4demo-briankim. This gives fail, since we should change the word index1 to index2 inside the ListExamples.java file. 

## Edit the code file ListExamples.java to fix the failing test (as a reminder, the error in the code is just that index1 is used instead of index2 in the final loop in merge)

<img src="lab4vimopen.png" width="300" height="40">

I opened the vim editor using the key: ```vim ListExamples.java <enter>```

<img src="lab4search.png" width="300" height="80">

Then, I searched for the word ```index1``` using the key: ```/index1 <enter>```. Then, I traversed down to the index1 that I want to change by pressing ```n``` key 6 times. ```n n n n n n```

<img src="lab4insert.png" width="300" height="120">

Now I have to replace the character 1 with 2. To do so, I pressed: ```l l l l l l``` to traverse over to the character 2, pressed ```x``` to delete the character 2, and pressed ```i``` to go to the insert mode followed by ```2``` to change it. In order to exit the insert mode, I pressed ```<esc>```, which brings me to normal mode. 

<img src="lab4save.png" width="300" height="120">

Because I am done changing the error, I pressed ```:wq <enter>``` to save and exit the vim editor. 

## Run the tests, demonstrating that they now succeed

<img src="lab4run.png" width="500" height="150">

Now that I am back to the terminal with the error fixed, I run the test by pressing ```bash test.sh <enter>```. This runs the test, and the result proves that the vim editor change has worked successfully. 

## Commit and push the resulting change to your Github account

<img src="lab4git2.png" width="500" height="300">

With the changed code, I updated the code using git. This was done pressing ```git add . <enter>``` which . at the end means adding all the changes. Then, I commited the added changes using ```git commit -m"success" <enter>```. This commit was then pushed to the github by the key ```git push <enter>```. 
