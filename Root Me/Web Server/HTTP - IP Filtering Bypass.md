<img width="1903" height="877" alt="image" src="https://github.com/user-attachments/assets/1447e757-d1d6-440e-a369-64cd625f4c9f" />

It's clear that only local users will be able to access the page and somehow I need to bypass the IP filters. I referred to [this](https://aditya-chauhan17.medium.com/how-to-bypass-ip-restriction-41040032225e) and intercepted the request in Burpsuite

<img width="1917" height="1018" alt="image" src="https://github.com/user-attachments/assets/0c8fd616-25be-4d74-92c0-fccd3a5c3b01" />

After sending this request to the Repeater, I added `X-Forwarded-For: 192.168.0.1`. 

`X-Forwarded-For` is basically a way for the proxy to tell the server your real IP address. An attacker can craft a request with a fake `X-Forwarded-For` value and pretend to be another IP that lets them bypass IP filters

<img width="1919" height="1014" alt="image" src="https://github.com/user-attachments/assets/b2cac034-2c58-4c77-a667-7020be5e5d73" />

Thus, the flag for this challenge is `Ip_$po0Fing`

