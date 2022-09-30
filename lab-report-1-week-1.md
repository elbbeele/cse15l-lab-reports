# Week 1 Lab Report
## Logging in to Course-Specific Account on ieng6


### *Installing VSCode*

1. First download VSCode through their website: [VSCode](https://code.visualstudio.com/)
2. Once you downloaded VSCode, you may see a screen like this after choosing the settings you prefer (dark mode, light mode, etc)

![Image](https://elbbeele.github.io/cse15l-lab-reports/installingVS.png)


### *Remotely Connecting*

1. Once you have VSCode open, open your new terminal by going to “terminal” in the top left menu bar and clicking the “new terminal" option
2. After you have your terminal open, type in “ssh cs15lfa22zz@ieng6.ucsd.edu” but instead of “zz,” substitute your account ID. 
3. If by chance, it asks when you want to continue connecting, type in “yes” and press enter
4. Afterwards, it will ask for your password. It will be easier for you to write your password down somewhere else and copy/paste because there is no visibility for your password. 
5. Once you are logged in, you will be on the remote server, and you will see something similar to the image below. 

![Image](https://elbbeele.github.io/cse15l-lab-reports/remoteConnect.png)
![Image](https://elbbeele.github.io/cse15l-lab-reports/loggedIn.png)

### *Trying Some Commands*

1. Once you are logged in the server, you can try out some commands!
2. Some examples you can try are:
```
cd~
cd
ls -lat
ls -a
ls /home/linux/cs15lfa22/cs15lfa22zz (where zz is another student’s account ID)
cp /home/linux/ieng6/cs15lfa22/public/hello.txt ~/
cat /home/linux/ieng6/cs15lfa22/public/hello.txt
```
3. These examples are shown in the image below!

![Image](https://elbbeele.github.io/cse15l-lab-reports/commandsEx.png)

### *Moving Files with scp*
1. First create a new file in your client (your computer) called "WhereAmI.java"
2. Copy paste the content below into the file.
```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```
3. Use these commands to compile and run "WhereAmI.java" in your client account. You will see a result similar to the image below.

```
javac WhereAmI.java
java WhereAmI
```
![Image](https://elbbeele.github.io/cse15l-lab-reports/compileInClient.png)

5. It is important to be able to copy files from your client to your server in case you need to access them in your server. You will realize that once you log in to your server, you will not be able to access "WhereAmI.java" because this file is in your client account. You can check this by using the command "ls" in your server account to check if the file exists or not
6. In order to copy, use this command:

``` 
scp WhereAmI.java cs15lfa22zz@ieng6.ucsd.edu:~/
```
7. Once you press enter, you will be asked to input the password for your server account. 
8. Now try the "ssh" command to log into your server account and the "ls" command to check if you can see "WhereAmI.java" under your server account. It should look similar to the image below.

![Image](https://elbbeele.github.io/cse15l-lab-reports/scp.png)

9. Once you see the file under your server account, you will be able to compile and run the file under your server. Please check the image below

![Image](https://elbbeele.github.io/cse15l-lab-reports/compileInServer.png)

### *Setting a SSH Key*

1. It is often too time consuming to continue to copy/paste your password every time you try to log in or use the "scp" command. In this situation, we can set an empty password instead
2. exit your server account by typing "exit" command 
3. In your client account, type the command "ssh-keygen". Once you do, it will prompt you to "Enter file in which to save the key (/Users/<username>/.ssh/id-rsa):"
4. Copy and paste the phrase inside the () and press enter
5. It will then prompt you to "Enter passphrase (empty for no passphrase):". In this step, press enter twice. 
6. You will then see something similar to the image below.
  
![Image](https://elbbeele.github.io/cse15l-lab-reports/sshKeyGen.png)
  
7. Now, log into your server account with "ssh" and enter your password 
8. Once you are on your server, type in command, "mkdir .ssh" and log out using "exit" command
9. once you are back on your client account, you will be able to use the "scp" or "ssh" command without having to copy and paste your password
  
```
  scp /Users/<username>/.ssh/id_rsa.pub cs15lfa22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys
 ```
 
![Image](https://elbbeele.github.io/cse15l-lab-reports/scp.png)
 
  
### *Optimizing Remote Running*
1. There are multiple ways to save time when using the terminal.
2. A few ways are listed below:
```
1. Using the arrow keys to access previous commands you have already tried
2. using multiple commands at once by separating them with ";"
```

![Image](https://elbbeele.github.io/cse15l-lab-reports/optimize.png)
