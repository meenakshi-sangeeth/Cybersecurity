# substitution0

## Challenge Description

A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher?
Download the message here

## Hints

Try a frequency attack. An online tool might help

## Solution

```bash
 ZGSOCXPQUYHMILERVTBWNAFJDK 

Qctcnrel Mcptzlo ztebc, fuwq z ptzac zlo bwzwcmd zut, zlo gtenpqw ic wqc gccwmc
xtei z pmzbb szbc ul fqusq uw fzb clsmebco. Uw fzb z gcznwuxnm bsztzgzcnb, zlo, zw
wqzw wuic, nlhlefl we lzwntzmubwb—ex sentbc z ptczw rtukc ul z bsuclwuxus reulw
ex aucf. Wqctc fctc wfe tenlo gmzsh brewb lczt elc cjwtciuwd ex wqc gzsh, zlo z
melp elc lczt wqc ewqct. Wqc bszmcb fctc cjsccoulpmd qzto zlo pmebbd, fuwq zmm wqc
zrrcztzlsc ex gntlubqco pemo. Wqc fcupqw ex wqc ulbcsw fzb actd tcizthzgmc, zlo,
wzhulp zmm wqulpb ulwe selbuoctzwuel, U senmo qztomd gmzic Ynruwct xet qub eruluel
tcbrcswulp uw.

Wqc xmzp ub: ruseSWX{5NG5717N710L_3A0MN710L_357GX9XX}
```
A *frequency attack* is a cryptanalysis technique used to break substitution ciphers by studying the frequency of letters or groups of letters in the encrypted message (ciphertext)

As the hint suggested, I did a frequency attack using an [online frequency analysis tool](https://www.dcode.fr/frequency-analysis) and voilà I got the flag :)

![image](https://github.com/user-attachments/assets/7d3cb5b4-6f29-4c66-8d2b-58c8db1a3f41)


Thus the flag for this challenge is `picoCTF{5UB5717U710N_3V0LU710N_357BF9FF}`
