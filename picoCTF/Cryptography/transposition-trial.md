# transposition-trial

## Challenge Description

Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.
Download the corrupted message here.

## Hints

Split the message up into blocks of 3 and see how the first block is scrambled

## Solution

I opened message.txt which gave me the following string
```bash
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V6E5926A}4
```

Since the challenge mentioned that the first word is three letters long, it was easy enough to work out  that "heT" must correspond to "The". The challenge also mentioned that every block of 3 got scrambled around. So I tried descrambling the string by dividing it into block of 3, as the hint suggested
```bash
["heT", "fl ", "g a", "s i", "icp", "CTo", "{7F", "4NR", "P05", "1N5", "_16", "_35", "P3X", "51N", "3_V", "9AA", "B1F", "8}7", "%"]
```
Initially I ignored the spaces in the string and only focused on the letters so I wasn't getting meaningful. After it clicked that I need to consider the spaces as well, it was easy to find the pattern. For every group of 3 characters, they were scrambled such that the last character became the first, the first became the second, and the second became the third. In short `abc -> cab`

Using this pattern I decoded each block manually (using pen and paper seemed more fun :) )
```bash
"heT" ->  "The"
"fl " ->  " fl"
"g a" ->  "ag "
"s i" ->  "is "
"icp" ->  "pic"
"CTo" ->  "oCT"
```
This confirmed I was on the right track. I applied the same pattern to the rest of the string and I got the following result

```bash
The flag is picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178}
```

Thus the flag for this challenge is `picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178} `
