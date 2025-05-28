# Safe Opener

## Challenge Description

Can you open this safe?
I forgot the key to my safe but this program is supposed to help me with retrieving the lost key. Can you help me unlock my safe?
Put the password you recover into the picoCTF flag format like:
picoCTF{password}

## Solution

```bash
import java.io.*;
import java.util.*;  
public class SafeOpener {
    public static void main(String args[]) throws IOException {
        BufferedReader keyboard = new BufferedReader(new InputStreamReader(System.in));
        Base64.Encoder encoder = Base64.getEncoder();
        String encodedkey = "";
        String key = "";
        int i = 0;
        boolean isOpen;
        

        while (i < 3) {
            System.out.print("Enter password for the safe: ");
            key = keyboard.readLine();

            encodedkey = encoder.encodeToString(key.getBytes());
            System.out.println(encodedkey);
              
            isOpen = openSafe(encodedkey);
            if (!isOpen) {
                System.out.println("You have  " + (2 - i) + " attempt(s) left");
                i++;
                continue;
            }
            break;
        }
    }
    
    public static boolean openSafe(String password) {
        String encodedkey = "cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz";
        
        if (password.equals(encodedkey)) {
            System.out.println("Sesame open");
            return true;
        }
        else {
            System.out.println("Password is incorrect\n");
            return false;
        }
    }
}
```
### Code Analysis

- User is prompted for a password.
- The password is encoded in Base64.
- The encoded password is compared with a hardcoded Base64 string. (`cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz`)
- If it matches, the safe opens.
- If not, the user gets up to 3 attempts.

So to get the password all I need to do is decode the Base64 string

![image](https://github.com/user-attachments/assets/2cd64c25-7c94-4092-bc1f-76b9d38fe990)

Thus the flag for this challenge is `picoCTF{pl3as3_l3t_m3_1nt0_th3_saf3}`
