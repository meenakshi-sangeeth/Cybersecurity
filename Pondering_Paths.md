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

To complete the challenge, I needed to move to the correct directory usind `cd` and then execute the program `/challenge/run`. To get the correct directory, I executed the following command: 
`/challenge/run`
This gave the following output
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
After that I executed the command `run` which gave me the flag

###3. Position Thy Self

##Challenge

To collect the flag by executing the `/challenge/run` program from a specific path

##Thought Process

To complete the challenge, I needed to move to the correct directory usind `cd` and then execute the program `/challenge/run`. To get the correct directory, I executed the following command: 
`/challenge/run`
This gave the following output
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
After that I executed the command `run` which gave me the flag
