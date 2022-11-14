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
//image for first change

For the change in the photo above, this is the first occurance of "start" in the file, so commands 1-5 led up to this change. After getting into the vim of the file, it starts off as normal mode of vim. After typing "/start <enter>" the cursor finds the first occurance of "start" in the file. When you type "dw", also in normal mode, it deletes the whole word. Now, you can switch into insert mode to type in the word "base". To do that, you can press i to enter the mode, and type out the word immediately.

// image for second change
For this change, you can use pressing n to find the other occurances of "start". Once, found, you can delete the word using "dw" and enter insert mode using "i." After typing out the word "base," you can press esc to go back into normal mode.

## Part 2
