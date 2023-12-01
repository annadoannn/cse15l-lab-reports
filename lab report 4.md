# Lab Report 4 -- Vim
__By Anna Doan__

We were instructed to do steps 4-9 from [week 7 lab](https://ucsd-cse15l-f23.github.io/week/week7/#week7-lab-report)

- feedback addressed: for each step, summarize the commands you ran and what the effect of those key presses were

## Step 4 -- Log into ieng6
I typed `ssh cs15lfa23ht@ieng6.ucsd.edu`, then `<enter>` to execute. 

The effect of these key presses resulted in logging into my ieng6 account without a password, hence the SSH command. 
![image](lab4.png)

## Step 5 -- Clone your fork of the repository from your Github account (using the SSH URL)
I typed `git clone git@github.com:annadoannn/lab7.git<enter>`.

By using the `git clone <SSH URL here>` command, it cloned my fork of the repository from my GitHub account to my ieng6 server workspace. 
![image](lab4-git.png)

## Step 6 -- Run the tests, demonstrating that they fail
I typed `cd lab7<enter>` to change from my remote home directory to the lab7 directory from the git repository I cloned. 

Then, I typed `bash test.sh<enter>`, to run the test script. The `bash` command runs the `test.sh` bash script. 
![image](lab4-bash.png)

## Step 7 -- Edit the code file to fix the failing test
I typed `vim ListExamples.java<enter>` to enter the text editor from the terminal and edit `ListExamples.java`:
![image](lab4-vim1.png)
which led me to here:
![image](lab4-vim2.png)
(the screenshot is when I entered into `vim`)

Then, I typed `<shift+g>` which takes me to the end of the `ListExamples.java` file. 

I proceeded with `<up><up><up><up><up><up>` to get to the line that contained the bug. 
Then, I continued with `<shift+e>` to get to the end of the first word, `<x>` to delete a character, `<a>` to go into insert mode, `<left>` to adjust curser, `<2>` to insert 2 and fix the bug, then `<esc> `to go back to normal mode.
![image](lab4-vim3.png)

Then, I typed `<:wq> <enter>` to save my changes and exit out of vim. 

## Step 8 -- Run the tests, demonstrating that they now succeed
I ran the test again by typing `bash test.sh<enter>`. 
![image](lab4-vim4.png)
It shows that the tests succeeded. 


## Step 9 -- Commit and push the resulting change to your Github account (you can pick any commit message!)
I typed `git add ListExamples.java<enter>` to take my modified `ListExamples.java` file and place the modified version in a staging area for the next commit. 
![image](lab4-git1.png)

Then, I typed `git commit -m "it works now"<enter>`. `git commit` saves the staged changes as new commit in the version history. A commit is a snapshot of the changes a user has made. The `-m "it works now"` that follows is the commit message. This message, "it works now", serves as a quick note about the changes I've made in that commit. 

Then, I proceeded to push the change into GitHub by typing `git push<enter>`. By doing this, I upload my local commits to a remote repository such as GitHub.
![image](lab4-git2.png)



