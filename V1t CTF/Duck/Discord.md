## Challenge

Join our Discord and look at the duck :>

## Solution

I got the following on copying duck emojies from announcements, updates and ticket channels

```bash
:v0::v1::v1::v1::v0::v1::v1::v0::v0::v0::v1::v1::v0::v0::v0::v1::v0::v1::v1::v1::v0::v1::v0::v0::v0::v1::v1::v1::v1::v0::v1::v1::v0::v1::v1::v0::v0::v1::v0::v0::v0::v0::v1::v1::v0::v0::v0::v1::v0::v0::v1::v1::v0::v1::v0::v1::v0::v0::v1::v1::v0::v1::v0::v1::v0::v1::v1::v0::v0::v0::v1::v1::v0::v0::v1::v1::v0::v0::v0::v0::v0::v1::v1::v1::v0::v0::v1::v0::v0::v1::v1::v0::v0::v1::v0::v0::v0::v1::v1::v1::v1::v1::v0::v1:
```

Formed binary from the above pattern and converted into text

```bash
s = ":v0::v1::v1::v1::v0::v1::v1::v0::v0::v0::v1::v1::v0::v0::v0::v1::v0::v1::v1::v1::v0::v1::v0::v0::v0::v1::v1::v1::v1::v0::v1::v1::v0::v1::v1::v0::v0::v1::v0::v0::v0::v0::v1::v1::v0::v0::v0::v1::v0::v0::v1::v1::v0::v1::v0::v1::v0::v0::v1::v1::v0::v1::v0::v1::v0::v1::v1::v0::v0::v0::v1::v1::v0::v0::v1::v1::v0::v0::v0::v0::v0::v1::v1::v1::v0::v0::v1::v0::v0::v1::v1::v0::v0::v1::v0::v0::v0::v1::v1::v1::v1::v1::v0::v1:"
flag = s.replace("v", "").replace(":", "")
print(flag)
```
<img width="1733" height="587" alt="image" src="https://github.com/user-attachments/assets/5160b44e-6735-4372-a69e-1a8cce48316d" />

Flag: `v1t{d155c0rd}`


