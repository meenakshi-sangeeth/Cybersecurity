# vault-door-3

## Challenge Description

This vault uses for-loops and byte arrays. The source code for this vault is here: VaultDoor3.java

## Hints

Make a table that contains each value of the loop variables and the corresponding buffer index that it writes to.

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


sadwf
