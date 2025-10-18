Before starting the challenge, I looked up what exactly directory indexing is. **Directory indexing** is what happens when you visit a URL that maps to a folder on a web server and there is no index file (like   index.html  ). The server may return an auto-generated page that lists the files and folders inside. That can leak sensitive files and give attackers an easy map of the site structure

I started by inspecting the source code

<img width="1917" height="958" alt="image" src="https://github.com/user-attachments/assets/d08b7089-846b-41b1-b91e-973bc153d251" />

As the comment suggested, I added `/admin/pass.html` to the path

<img width="1903" height="971" alt="image" src="https://github.com/user-attachments/assets/271dce05-a786-46ee-85f9-a36292dc2753" />

*sigh*

Well, I played around for a while and removed the `/pass.html` and voila!

<img width="1919" height="967" alt="image" src="https://github.com/user-attachments/assets/4689ccce-2e66-436d-a1c9-e032def9f6cf" />

I checked what's inside `backup/`

<img width="1919" height="963" alt="image" src="https://github.com/user-attachments/assets/899a7f64-96a5-45ff-acfb-a9b3ad899d32" />

<img width="1919" height="960" alt="image" src="https://github.com/user-attachments/assets/822d8c97-8e12-4020-a405-90b10f49fae5" />

The flag for this challenge is 'LINUX`


