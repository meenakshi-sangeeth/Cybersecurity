# waves over lambda

## Challenge Description

We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with nc jupiter.challenges.picoctf.org 39894

## Hint

Flag is not in the usual flag format

## Solution

```bash
~# nc jupiter.challenges.picoctf.org 39894
-------------------------------------------------------------------------------
gvmsiyln uziz wn tvxi hcys - hizoxzmgt_wn_g_vrzi_cykfqy_yshcgsltxz
-------------------------------------------------------------------------------
fzlpzzm xn luziz pyn, yn w uyrz ycizyqt nywq nvkzpuziz, luz fvmq vh luz nzy. fznwqzn uvcqwms vxi uzyiln lvszluzi luivxsu cvms dziwvqn vh nzdyiylwvm, wl uyq luz zhhzgl vh kyawms xn lvcziyml vh zygu vluzi'n tyimnymq zrzm gvmrwglwvmn. luz cyptziluz fznl vh vcq hzccvpnuyq, fzgyxnz vh uwn kymt tzyin ymq kymt rwilxzn, luz vmct gxnuwvm vm qzga, ymq pyn ctwms vm luz vmct ixs. luz yggvxmlyml uyq fivxsul vxl ycizyqt y fvj vh qvkwmvzn, ymq pyn lvtwms yiguwlzglxiycct pwlu luz fvmzn. kyicvp nyl givnn-czsszq iwsul yhl, czymwms ysywmnl luz kwbbzm-kynl. uz uyq nxmazm guzzan, y tzccvp gvkdczjwvm, y nliywsul fyga, ym yngzlwg yndzgl, ymq, pwlu uwn yikn qivddzq, luz dyckn vh uymqn vxlpyiqn, iznzkfczq ym wqvc. luz qwizglvi, nylwnhwzq luz ymguvi uyq svvq uvcq, kyqz uwn pyt yhl ymq nyl qvpm ykvmsnl xn. pz zjguymszq y hzp pviqn cybwct. yhlzipyiqn luziz pyn nwczmgz vm fvyiq luz tygul. hvi nvkz izynvm vi vluzi pz qwq mvl fzswm luyl sykz vh qvkwmvzn. pz hzcl kzqwlylwrz, ymq hwl hvi mvluwms fxl dcygwq nlyiwms. luz qyt pyn zmqwms wm y nzizmwlt vh nlwcc ymq zjoxwnwlz fiwccwymgz. luz pylzi nuvmz dygwhwgycct; luz nat, pwluvxl y ndzga, pyn y fzmwsm wkkzmnwlt vh xmnlywmzq cwsul; luz rzit kwnl vm luz znnzj kyinu pyn cwaz y syxbt ymq iyqwyml hyfiwg, uxms hivk luz pvvqzq iwnzn wmcymq, ymq qiydwms luz cvp nuvizn wm qwyduymvxn hvcqn. vmct luz scvvk lv luz pznl, fivvqwms vrzi luz xddzi izyguzn, fzgykz kviz nvkfiz zrzit kwmxlz, yn wh ymszizq ft luz yddivygu vh luz nxm.
```
My first instinct was to do a frequency attack. A *frequency attack* is a cryptanalysis technique used to break substitution ciphers by studying the frequency of letters or groups of letters in the encrypted message (ciphertext)

I used an online [frequency analysis tool](https://www.dcode.fr/frequency-analysis)

![image](https://github.com/user-attachments/assets/f0f80137-e854-40e0-a332-bbb96738a200)

Well my instinct was right. However I did waste a lot of time trying to submit the flag since it said incorrect flag everytime i entered `picoCTF{frequency_is_c_over_lambda_agflcgtyue}` until I paid attention to the hint and realised I need not wrap the flag in picoCTF{}.

Thus the flag for this challenge is `frequency_is_c_over_lambda_agflcgtyue`
