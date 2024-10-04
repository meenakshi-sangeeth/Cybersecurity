#Pondering Paths

##1. The Root

###Challenge

To collect the flag by invoking pwn program using its absolute path.

###Thought Process

The challenge required required running pwn program using its **absolute path**. In Linux, an absolute path starts from the root directory (`/`) and specifies the complete location of a file or program.

###Solution

I typed in the following command: 
```bash
/pwn
```
Upon execution, I received the flag.

##2. Program and Absolute Paths

###Challenge

To collect the flag by invoking the file named `run` within the `/challenge` directory.

###Thought Process

I understood that the challenge program `run` was located in the `/challenge` directory, and I needed to execute it by invoking its **absolute path**. 
Thus I used the following command
```bash
/challenge/run
```
Upon execution, I got the flag.

###3. Position Thy Self

##Challenge

To collect the flag by executing the `/challenge/run` program from a specific path

##Thought Process

To complete the challenge, I needed to move to the correct directory using `cd` and then execute the program `/challenge/run`. To get the correct directory, I executed the following command: 
`/challenge/run`
This gave me the following output
```bash
Incorrect...
You are not currently in the /usr/share/build-essential directory.
Please use the `cd` utility to change directory appropriately.
```
Thus I found out the correct directory which is usr/share/build-essential

###Solution 

I navigated to the right directory using the command
```bash
cd usr/share/build-essential
```
After that I executed the command `/challenge/run` which gave me the flag

###4. Postition Elsewhere

##Challenge

To collect the flag by executing the `/challenge/run` program from a specific path 

##Thought Process

To complete the challenge, I needed to move to the correct directory using `cd` and then execute the program `/challenge/run`. To get the correct directory, I executed the following command:
`/challenge/run`
This gave me the following output
```bash
Incorrect...
You are not currently in the /var directory.
Please use the `cd` utility to change directory appropriately.
```
Thus I found out the correct directory which is /var

###Solution

I navigated to the right directory using the command
```bash
cd /var
```
After that I executed the command `/challenge/run` which gave me the flag

#5. Position Yet Elsewhere

##Challenge

To collect the flag by executing the `/challenge/run` program from a specific path 

##Thought Process

To complete the challenge, I needed to move to the correct directory using `cd` and then execute the program `/challenge/run`. To get the correct directory, I executed the following command:
`/challenge/run`
This gave me the following output
```bash
Incorrect...
You are not currently in the /etc directory.
Please use the `cd` utility to change directory appropriately.
```
Thus I found out the correct directory which is /etc

###Solution

I navigated to the right directory using the command
```bash
cd /etc
```
After that I executed the command `/challenge/run` which gave me the flag

#6. Implicit Relative Paths, From /

##Challenge

To collect the flag by running `/challenge/run` using a relative path while having a current working directory of `/`

##Thought Process

I knew that relative path is based on the current working directory (cwd) and doesn’t start with `/`. It was mentioned that cwd is `/`. So I would have to navigate to the root directory using the command `cd /`. Since the challenge was to run `/challenge/run` using a relative path, I needed to figure out the path from `/` to the `run` file. A hint was given that said the relative path starts with the letter "c". Thus I figured that the file is most likely to be in the `challenge` folder and knowing that `/challenge/run` is an absolute path, I would have to remove the leading `/`, so that the relative path would become `challenge/run`.

###Solution

I navigated to the cwd using the command
```bash
cd /
```
After that I used the following command 
```bash
challenge/run
```
Upon execution, I got the flag

#7. Explicit Relative Paths, From /

##Challenge

To collect the flag by running `challenge/run` using `.` in the relative path while having a current working directory of `/`

##Thought Process

I knew that `.` represents the current directory and relative path is based on the current working directory (cwd) and doesn’t start with `/`. It was mentioned that cwd is `/`. So I would have to navigate to the root directory using the command `cd /`. Since the challenge was to run `challenge/run` using `.` in the relative path, I would have to prepend `./` to the relative path `challenge/run`.

###Solution

I navigated to the cwd using the command
```bash
cd /
```
After that I used the following command 
```bash
./challenge/run
```
Upon execution, I got the flag


#8. Implicit Relative Path

##Challenge

To collect the flag by executing `run` program using a relative path while having a current working directory of `/challenge`

##Thought Process

First I would have to navigate to the cwd using the command `cd /challenge`.  I knew that simply executing the command `run` within `/challenge` directory will not invoke `/challenge/run` since Linux explicitly avoids automatically looking in the current directory when you provide a "naked" path. I also knew that `.` represents the current directory. Thus I figured I would have to prepend `./` to the command `run` within `/challenge` directory.

###Solution

I navigated to the cwd using the command
```bash
cd /challenge
```
After that I used the following command 
```bash
./run
```
Upon execution, I got the flag

#9. Home Sweet Home

##Challenge

To collect the flag by executing `/challenge/run` command by specifying a file path as an argument with the following constraints:
1. Your argument must be an absolute path.
2. The path must be inside your home directory.
3. Before expansion, your argument must be three characters or less

##Thought Process

I knew that `~` is shorthand for `/home/hacker`, which is my home directory in Dojo. Since the path had to be within my home directory and the argument could be only three characters or less, I figured that using `~` would meet the given constraints. Thus I would have to prepend `~/` to the file name which should be a single character to meet the constraints.

###Solution

I used the following command
```bash
/challenge/run ~/f
```
Upon execution, I got the flag
