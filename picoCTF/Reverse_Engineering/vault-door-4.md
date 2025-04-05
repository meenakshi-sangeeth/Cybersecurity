# vault-door-4

## Challenge Description

This vault uses ASCII encoding for the password. The source code for this vault is here: VaultDoor4.java

## Hints

1. Use a search engine to find an "ASCII table".
2. You will also need to know the difference between octal, decimal, and hexadecimal numbers

## Solution

```bash
import java.util.*;

class VaultDoor4 {
    public static void main(String args[]) {
        VaultDoor4 vaultDoor = new VaultDoor4();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
	String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
	if (vaultDoor.checkPassword(input)) {
	    System.out.println("Access granted.");
	} else {
	    System.out.println("Access denied!");
        }
    }

    // I made myself dizzy converting all of these numbers into different bases,
    // so I just *know* that this vault will be impenetrable. This will make Dr.
    // Evil like me better than all of the other minions--especially Minion
    // #5620--I just know it!
    //
    //  .:::.   .:::.
    // :::::::.:::::::
    // :::::::::::::::
    // ':::::::::::::'
    //   ':::::::::'
    //     ':::::'
    //       ':'
    // -Minion #7781
    public boolean checkPassword(String password) {
        byte[] passBytes = password.getBytes();
        byte[] myBytes = {
            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 070 , 0146,
            '4' , 'a' , '6' , 'c' , 'b' , 'f' , '3' , 'b' ,
        };
        for (int i=0; i<32; i++) {
            if (passBytes[i] != myBytes[i]) {
                return false;
            }
        }
        return true;
    }
}
```
The `myBytes` array contains 32 bytes in different formats - decimal, hexadecimal, octal and character literals. In order to get the password, I'll have to convert each of them to ASCII format as suggested by the hint

![image](https://github.com/user-attachments/assets/a69f9f73-6323-4f71-beb6-2928109c44e3)

```bash
106 -> 'j'
85  -> 'U'
53  -> '5'
116 -> 't'
95  -> '_'
52  -> '4'
95  -> '_'
98  -> 'b'

0x55 -> 'U'
0x6e -> 'n'
0x43 -> 'C'
0x68 -> 'h'
0x5f -> '_'
0x30 -> '0'
0x66 -> 'f'
0x5f -> '_'

0142 -> 98  -> 'b'
0131 -> 89  -> 'Y'
0164 -> 116 -> 't'
063  -> 51  -> '3'
0163 -> 115 -> 's'
0137 -> 95  -> '_'
070  -> 56  -> '8'
0146 -> 102 -> 'f'
```
On combining all the characters I got "jU5t_4_bUnCh_0f_bYt3s_8f4a6cbf3b"

Thus the flag for this challenge is `picoCTF{jU5t_4_bUnCh_0f_bYt3s_8f4a6cbf3b}`
