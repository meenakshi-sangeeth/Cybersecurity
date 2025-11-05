## Challenge

Ts fr lwk pmo gng

Gnp.egami

## Solution

I started by checking the file structure

```bash
$ file gnp.egami
gnp.egami: data
$xxd gnp.egami | head -5
00000000: c282 6042 c2ae 444e 4549 0000 0000 5dc2  ..`B..DNEI....].
00000010: 93c3 a915 357a c388 c2b4 0fc3 bc41 c391  ....5z.......A..
00000020: 28c2 95c3 824a 20c3 a8c2 944a c3a1 2510  (....J ....J..%.
00000030: 744a 2570 c292 c288 3a25 12c2 b849 441d  tJ%p....:%...ID.
00000040: 12c2 895c 24c2 a20e c289 44c2 ae12 50c2  ...\$.....D...P.
$ xxd gnp.egami | tail -5
000016d0: 0000 0561 c3bc 0bc2 8fc2 b100 0041 4d41  ...a.........AMA
000016e0: 6704 0000 00c3 a91c c38e c2ae 0042 4752  g............BGR
000016f0: 7301 0000 005b 260f 6400 0000 0608 2700  s....[&.d.....'.
00001700: 0000 c39c 0000 0052 4448 490d 0000 000a  .......RDHI.....
00001710: 1a0a 0d47 4e50 c289                      ...GNP..
```

I noticed `DNEI` at the start which is `IEND` (PNG end marker) backwards and `GNP` at the end which is just `PNG` backwards. And even the filename `gnp.egami` is `png.image` backwards. So I did byte reversal but that didn't work. Further on examining the hex dump, the bytes `c2`, `c3` indicate UTF-8 encoding artifacts. So I decoded the UTF-8 encoding first and then reversed it

```bash
with open('gnp.egami', 'rb') as f:
    data = f.read()
decoded = data.decode('utf-8', errors='ignore').encode('latin1')
reversed_data = decoded[::-1]
with open('final.png', 'wb') as f:
    f.write(reversed_data)
```

I opened `final.png`

<img width="220" height="39" alt="final" src="https://github.com/user-attachments/assets/b0662779-b525-4e4c-b4a1-6a6e723d0b49" />

Flag: `v1t{r3v_1mg_4ge}`
