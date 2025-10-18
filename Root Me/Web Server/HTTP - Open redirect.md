<img width="1490" height="664" alt="image" src="https://github.com/user-attachments/assets/44297255-304b-4bb2-b7df-4486a2fe01f6" />

Firstly, I intercepted the request using Burpsuite by clicking on "Facebook" and sent it to Repeater

<img width="1919" height="1017" alt="image" src="https://github.com/user-attachments/assets/3032eec2-199a-4ef0-8ecd-03acd00ee141" />

I noticed the `h` parameter and I checked if it's a hash

<img width="1878" height="596" alt="image" src="https://github.com/user-attachments/assets/96bc3a4a-c6c3-4269-a619-2a0baf69cdae" />

It indeed is an MD5 hash

<img width="1887" height="492" alt="image" src="https://github.com/user-attachments/assets/9a9044a0-3f23-404a-b2bb-95f580cfba2f" />

It took me a while to figure out what's actually happening. Basically the web page accepts a `url` parameter to redirect users and it tries to “protect” that redirect with a hash in the `h` parameter. Because the hash is just a plain MD5 of the URL, I can esaily craft a request that can make the server redirect to any site by supplying the correct hash for the chosen URL. So, I thought I'll redirect the server to Instagram for which I generated MD5 hash

<img width="1911" height="866" alt="image" src="https://github.com/user-attachments/assets/b282563e-5cc8-42fc-b470-816be732ac4d" />

Then I modified the HTTP request

<img width="1919" height="1020" alt="image" src="https://github.com/user-attachments/assets/fc29dab8-3657-4f06-8a33-c21e5e78c763" />

Thus, the flag for this challenge is `e6f8a530811d5a479812d7b82fc1a5c5`


