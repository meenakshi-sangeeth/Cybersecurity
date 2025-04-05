# la cifra de

## Challenge Description

I found this cipher in an old book. Can you figure out what it says? Connect with nc jupiter.challenges.picoctf.org 5726.

## Hints

1. There are tools that make this easy
2. Perhaps looking at history will help

## Solution

```bash
:~#  nc jupiter.challenges.picoctf.org 5726
Encrypted message:
﻿Ne iy nytkwpsznyg nth it mtsztcy vjzprj zfzjy rkhpibj nrkitt ltc tnnygy ysee itd tte cxjltk

Ifrosr tnj noawde uk siyyzre, yse Bnretèwp Cousex mls hjpn xjtnbjytki xatd eisjd

Iz bls lfwskqj azycihzeej yz Brftsk ip Volpnèxj ls oy hay tcimnyarqj dkxnrogpd os 1553 my Mnzvgs Mazytszf Merqlsu ny hox moup Wa inqrg ipl. Ynr. Gotgat Gltzndtg Gplrfdo

Ltc tnj tmvqpmkseaznzn uk ehox nivmpr g ylbrj ts ltcmki my yqtdosr tnj wocjc hgqq ol fy oxitngwj arusahje fuw ln guaaxjytrd catizm tzxbkw zf vqlckx hizm ceyupcz yz tnj fpvjc hgqqpohzCZK{m311a50_0x_a1rn3x3_h1ah3x6kp60egf}

Ehk ktryy herq-ooizxetypd jjdcxnatoty ol f aordllvmlbkytc inahkw socjgex, bls sfoe gwzuti 1467 my Rjzn Hfetoxea Gqmexyt.

Tnj Gimjyèrk Htpnjc iy ysexjqoxj dosjeisjd cgqwej yse Gqmexyt Doxn ox Fwbkwei Inahkw.

Tn 1508, Ptsatsps Zwttnjxiax tnbjytki ehk xz-cgqwej ylbaql rkhea (g rltxni ol xsilypd gqahggpty) ysaz bzuri wazjc bk f nroytcgq nosuznkse ol yse Bnretèwp Cousex.

Gplrfdo’y xpcuso butvlky lpvjlrki tn 1555 gx l cuseitzltoty ol yse lncsz. Yse rthex mllbjd ol yse gqahggpty fce tth snnqtki cemzwaxqj, bay ehk fwpnfmezx lnj yse osoed qptzjcs gwp mocpd hd xegsd ol f xnkrznoh vee usrgxp, wnnnh ify bk itfljcety hizm paim noxwpsvtydkse.
```
I noticed numbers like 1553, 1467, 1508 in the ciphertext and I figured they might be representing years since one of the hints said "Perhaps looking at history will help". Thus I googled "cipher 1553" and all the results pointed to  Vigenère ciphers. The years indeed matched with the history of  Vigenère cipher and hence I concluded that vigenère cipher is used to encrypt the message

The *Vigenère cipher* is a polyalphabetic substitution cipher, meaning it encrypts the same letter differently based on its position in the text. It uses a keyword to determine shifts in the alphabet

However in this case I didn't know the key to decipher the ciphertext. So used an online [vigenère breaker](https://guballa.de/vigenere-solver)

![image](https://github.com/user-attachments/assets/12d92dcc-f659-48bc-91ec-e520528658c0)

Thus the flag for this challenge is `picoCTF{b311a50_0r_v1gn3r3_c1ph3r6fe60eaa}`
