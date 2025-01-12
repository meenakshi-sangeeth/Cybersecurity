# Key Concepts

- Web Sockets

  Imagine you're on a call with a friend—once you connect, you can talk back and forth without hanging up each time you want to say something. This is how WebSockets work between your browser and a server. Instead of asking for information over and over (like sending emails back and forth), WebSockets keep the line open, making communication faster and smoother.

- HTTP vs. WebSockets

  - Traditional HTTP: Your browser asks the server for updates each time, like knocking on a door every few seconds to ask, "Any new messages?" This is slow and wastes resources.
  - WebSockets: Once connected, the server can send updates automatically without asking, like keeping the door open for instant updates

- Security Risks

  - Weak Authentication: If a WebSocket doesn't check who you are, attackers might sneak in and steal information.
  - Message Tampering: Without encryption, hackers can change messages being sent between the browser and server, possibly sending harmful commands.
  - Cross-Site Hijacking: Attackers might trick your browser into connecting to a bad server, stealing data or hijacking your connection.
  - Denial of Service (DoS): Attackers can flood the server with too many messages, making it slow or causing a crash.

 ![image](https://github.com/user-attachments/assets/f16122b4-6f6d-4be5-b451-1aef08f46db7)

  
