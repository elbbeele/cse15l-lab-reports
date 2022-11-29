# Week 7 Lab Report 4

## Part 1 

Task: changing the name of the "start" parameter and its uses to "base"

````
(in local terminal) type "vim DocSearchServer.java" <enter>
(inside vim) type “/start” <enter>
type "dw"
Press i
Type “base” 
<esc>
Press N, "dw", i (for each occurance of "base" that needs to be changed)
Type “base”
<esc>
Type ":wq"
````
### Step 1: type "vim DocSearchServer.java" <enter>
![Image](https://elbbeele.github.io/cse15l-lab-reports/step1VIM.png)
  
  For this step, it enters the normal mode for VIM, allowing you to view the code in the terminal instead of opening the file directly on VS Code. 
  
### Step 2: type "/start" <enter>
![Image](https://elbbeele.github.io/cse15l-lab-reports/step2VIM.png)
  
  For this step, it searches for the first occurance of "start" in the file on vim. Because we haven't asked to specifically be in a different mode of VIM, we are still in normal mode, which allows us to use these short cuts to find specific words or characters in the file. 
  
### Step 4: type "dw"
![Image](https://elbbeele.github.io/cse15l-lab-reports/step3VIM.png) 
  
  For this command, it deletes the whole word that the cursor is on before the command. By doing so, we can save time instead of deleting each character of "start". 
  
### Step 4: press i
![Image](https://elbbeele.github.io/cse15l-lab-reports/step4VIM.png)  
  
  For this step, it enters insert mode of vim, which allows you to change the actual code of the file by deleting, inserting, replacing, etc. By doing so, we can start changing the variable "start" to be called "base".

### Step 5: Type "base"
![Image](https://elbbeele.github.io/cse15l-lab-reports/step5VIM.png) 
  
  Now that the word "start" is deleted and we are in insert mode, we can start editing the file. We can directly type in "base" to change the variable.
  
### Step 6: <esc>
![Image](https://elbbeele.github.io/cse15l-lab-reports/step6VIM.png)
  
  In order to find the other occurances of "Start", we have to use the command in step 7. However, we cannot use these commands for what we intend for it to do in the "insert" mode of vim. We have to get back into the "normal" mode. In order to do that, we can just press the <esc> button.

### Step 7: Press N, "dw", i 
![Image](https://elbbeele.github.io/cse15l-lab-reports/step7part1VIM.png)

  For this step, the user can repeat these steps for each occurance of "Start" until they finish changing all the "starts" they want to change to "base." By pressing N in normal mode (you can find the next occurance of "start" that you want to change. 
 
![Image](https://elbbeele.github.io/cse15l-lab-reports/step7part2VIM.png)
 
  The photo above shows the next part of step 7, which is also deleting the whole word of "Start" inorder to change it to "base."
 
### Step 8: Type "base"
![Image](https://elbbeele.github.io/cse15l-lab-reports/step8VIM.png)
  
  For this step, you are just typing out "base" again in insert mode after step 7 of deleting the word. 

### Step 9: Type ":wq"
![Image](https://elbbeele.github.io/cse15l-lab-reports/step9VIM.png)
  
  For this step, you are saving your progress and exiting out of vim. Once you exit out of vim, you will see your terminal again like the photo above.


## Part 2
For the first option, it took me 30 seconds.
For the second option, it took me 40 seconds. 
  
I think I would prefer to use vim because if the number of edits I had to make was more than one, vim would be a lot more time efficient and effective to use. This is because there are a lot of user friendly shortcuts in vim that can make editing a lot easier. Furthermore, there are more flexible ways to edit a code in vim than manually in VS Code, so I think I would prefer vim. I think once I get more comfortable with using vim in general, the time it takes for me to do these tasks would decrease exponentially.
