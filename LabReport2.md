# Week 1 Lab Report
**Installing VScode**

![](Screen%20Shot%202022-09-29%20at%209.46.32%20AM.png)
1. Search up Vscode on internet browser
2. Follow instructions to download and install on your computer

**Remotely Connecting**

![](Screen%20Shot%202022-09-29%20at%2012.22.26%20PM.png)
1. Open VsCode terminal and login to server using command 
`ssh cs15lfa22zz@ieng6.ucsd.edu`
2. Type in password (you will not be able to see your text)

**Trying Some Commands**

![](Screen%20Shot%202022-09-29%20at%201.01.13%20PM.png)
1. Try running some commands on your remote computer as you would on your local system
2. `cp /home/linux/ieng6/cs15lfa22/public/hello.txt ~/` To Copy file 
3. `cat /home/linux/ieng6/cs15lfa22/public/hello.txt` To Paste File

**Moving Files with scp** 
![](Screen%20Shot%202022-09-29%20at%201.30.36%20PM.png)
1. Create a file with whatever contents ex. `WhereAmI.java`
2. Run Command `scp WhereAmI.java cs15lfa22zz@ieng6.ucsd.edu:~/` to copy file on to remote system
3. Compile and run using `javac WhereAmI.java; java WhereAmI`

**Setting an SSH Key**
![](Screen%20Shot%202022-09-29%20at%201.40.07%20PM.png)
1. Creates a pair of files public key and private key for easier login
2. Call command `ssh-keygen` 
3. Remember the key in which the file was saved ex. `/Users/joe/ .ssh/id_rsa`
4. Call command `ssh cs15lfa22dt@ieng6.ucsd.edu` and enter password
5. On server call `mkdir.ssh` and logout
6. Call command 
`scp /Users/joe/.ssh/id_rsa.pub cs15lfa22@ieng6.ucsd.edu:~/.ssh/authorized_keys`

**Optimizing Remote Running**
![](Screen%20Shot%202022-09-29%20at%201.53.01%20PM.png)
1. You can run multiple commands at once 
2. In one line; save file to remote computer and compile and run it remotely.
3. Using command `ssh cs15lfa22dt@ieng6.ucsd.edu; ssh cs15lfa22dt@ieng6.ucsd.edu "javac WhereAmI.java; java WhereAmI"`
