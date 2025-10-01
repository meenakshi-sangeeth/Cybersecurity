
### Challenge

To collect the flag by reading the `challenge` man page and finding the option that will give the flag

### Thought Process

I knew that man is short for manual, and will display (if available) the manual of the command you pass as an argument. I recalled that I can search through the manpage by hitting *n* to go to the next result and *N* to go to the previous result

### Solution

To display the manpage, I used the following command
```bash
man challenge
```
Upon execution, I got the manpage comprising of a large number of lines. I figured I'll have to search through the manpage in order to find the right argument. I tried hitting *n* and the part of lines containing "flag" were highlighted. Thus I kept hitting *n* until I found the following line

![cryptonite_taskphase_meenakshi/Screenshot 2024-10-09 173014.png](https://github.com/meenakshi-sangeeth/cryptonite_taskphase_meenakshi/blob/main/Screenshot%202024-10-09%20173014.png)


Then I used the following command
```bash
/challenge/challenge --tg
```
Upon execution, I got the flag
