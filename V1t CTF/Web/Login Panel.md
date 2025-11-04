## Challenge

https://tommytheduck.github.io/login

## Solution

From the source code I got the username and password hashes which were cracked using [CrackStation]

```bash

<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Login Panel</title>
</head>
<body>
  <script>
    async function toHex(buffer) {
      const bytes = new Uint8Array(buffer);
      let hex = '';
      for (let i = 0; i < bytes.length; i++) {
        hex += bytes[i].toString(16).padStart(2, '0');
      }
      return hex;
    }

    async function sha256Hex(str) {
      const enc = new TextEncoder();
      const data = enc.encode(str);
      const digest = await crypto.subtle.digest('SHA-256', data);
      return toHex(digest);
    }

    function timingSafeEqualHex(a, b) {
      if (a.length !== b.length) return false;
      let diff = 0;
      for (let i = 0; i < a.length; i++) {
        diff |= a.charCodeAt(i) ^ b.charCodeAt(i);
      }
      return diff === 0;
    }

    (async () => {
      const ajnsdjkamsf = 'ba773c013e5c07e8831bdb2f1cee06f349ea1da550ef4766f5e7f7ec842d836e'; // replace
      const lanfffiewnu = '48d2a5bbcf422ccd1b69e2a82fb90bafb52384953e77e304bef856084be052b6'; // replace

      const username = prompt('Enter username:');
      const password = prompt('Enter password:');

      if (username === null || password === null) {
        alert('Missing username or password');
        return;
      }

      const uHash = await sha256Hex(username);
      const pHash = await sha256Hex(password);

      if (timingSafeEqualHex(uHash, ajnsdjkamsf) && timingSafeEqualHex(pHash, lanfffiewnu)) {
        alert(username+ '{'+password+'}');
      } else {
        alert('Invalid credentials');
      }
    })();
  </script>
</body>
</html>
```

Username hash: `ba773c013e5c07e8831bdb2f1cee06f349ea1da550ef4766f5e7f7ec842d836e`
Password hash: `48d2a5bbcf422ccd1b69e2a82fb90bafb52384953e77e304bef856084be052b6`

<img width="1267" height="82" alt="image" src="https://github.com/user-attachments/assets/6c2870b9-0240-449b-ab94-68bbc721319d" />
<img width="1276" height="79" alt="image" src="https://github.com/user-attachments/assets/668ca5f3-0720-44e6-ac14-f7bc4535f8e4" />

Got the flag on entering credentials

Flag: `v1t{p4ssw0rd}`
