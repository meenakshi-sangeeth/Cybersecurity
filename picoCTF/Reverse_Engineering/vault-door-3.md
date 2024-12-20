# vault-door-3

## Challenge Description

This vault uses for-loops and byte arrays. The source code for this vault is here: VaultDoor3.java

## Hints

Make a table that contains each value of the loop variables and the corresponding buffer index that it writes to

## Thought Process

Let's inspect the attached file
```bash
public class VaultDoor3Solver {
    public static void main(String[] args) {
        // The target buffer after transformations
        String target = "jU5t_a_sna_3lpm18g947_u_4_m9r54f";

        // Reconstruct the input password
        char[] password = new char[32];
        char[] buffer = target.toCharArray();

        // Loop 1
        for (int i = 0; i < 8; i++) {
            password[i] = buffer[i];
        }

        // Loop 2
        for (int i = 8; i < 16; i++) {
            password[23 - i] = buffer[i];
        }

        // Loop 3
        for (int i = 16; i < 32; i += 2) {
            password[46 - i] = buffer[i];
        }

        // Loop 4
        for (int i = 31; i >= 17; i -= 2) {
            password[i] = buffer[i];
        }

        // Print the reconstructed password
        System.out.println("picoCTF{" + new String(password) + "}");
    }
}
```

### Analysis

A char[] buffer of length 32 is filled based on the input password through four loops:
- Loop 1 (i = 0 to 7):
  `buffer[i]=password.charAt(i)`
  The first 8 characters of the password are directly copied
  password[0..7]=buffer[0..7]
- Loop 2 (i = 8 to 15):
  `buffer[i]=password.charAt(23−i)`
  The next 8 characters are taken in reverse order from the range 15 to 8
  password[15..8]=buffer[8..15]
- Loop 3 (i = 16 to 31 with step 2):
  `buffer[i]=password.charAt(46−i)`
  Every second character from password (index 46 - i) is copied to the buffer
  password[30,28,26,...,16]=buffer[16,18,20,...,30]
- Loop 4 (i = 31 to 17 with step -2):
  `buffer[i]=password.charAt(i)`
  Characters from password (index i) are directly copied into the buffer, starting at the end and moving backward
  password[31,29,27,...,17]=buffer[31,29,27,...,17]

Now I'll have to work backward from the final string "jU5t_a_sna_3lpm18g947_u_4_m9r54f" to reconstruct the input password

## Solution
```bash
password[0] = buffer[0] = 'j'
password[1] = buffer[1] = 'U'
password[2] = buffer[2] = '5'
password[3] = buffer[3] = 't'
password[4] = buffer[4] = '_'
password[5] = buffer[5] = 'a'
password[6] = buffer[6] = '_'
password[7] = buffer[7] = 's'

password[15] = buffer[8] = 'n'
password[14] = buffer[9] = 'a'
password[13] = buffer[10] = '_'
password[12] = buffer[11] = '3'
password[11] = buffer[12] = 'l'
password[10] = buffer[13] = 'p'
password[9] = buffer[14] = 'm'
password[8] = buffer[15] = '1'

password[30] = buffer[16] = '8'
password[28] = buffer[18] = '9'
password[26] = buffer[20] = '7'
password[24] = buffer[22] = '_'
password[22] = buffer[24] = '_'
password[20] = buffer[26] = 'm'
password[18] = buffer[28] = 'r'
password[16] = buffer[30] = '4'

password[31] = buffer[31] = 'f'
password[29] = buffer[29] = '5'
password[27] = buffer[27] = '9'
password[25] = buffer[25] = '4'
password[23] = buffer[23] = 'u'
password[21] = buffer[21] = '4'
password[19] = buffer[19] = 'g'
password[17] = buffer[17] = 'g'
```
The password is `jU5t_a_s1mpl3_an4gr4m_4_u_79958f`

Thus the flag for this challenge is `picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_79958f}`
