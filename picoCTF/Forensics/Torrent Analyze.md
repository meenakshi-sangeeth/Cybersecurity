# Torrent Analyze

## Challenge Description

SOS, someone is torrenting on our network.
One of your colleagues has been using torrent to download some files on the company’s network. Can you identify the file(s) that were downloaded? The file name will be the flag, like picoCTF{filename}. Captured traffic

## Hints

- Download and open the file with a packet analyzer like Wireshark.
- You may want to enable BitTorrent protocol (BT-DHT, etc.) on Wireshark. Analyze -> Enabled Protocols
- Try to understand peers, leechers and seeds. Article
- The file name ends with .iso
  
## Solution

I opened the `torrent.pcap` file in Wireshark and first enabled the proper protocol for analysis. As the hint suggested, I made sure BT-DHT (Bittorrent DHT Protocol) is enabled, which allows Wireshark to properly decode and display the BitTorrent Distributed Hash Table protocol packets.

I [learned](https://www.youtube.com/watch?v=xg0RHkuTwlQ) that in BitTorrent protocols, each torrent is identified by an `info_hash`, a SHA-1 hash of the torrent file that uniquely identifies the content being shared.

I used Wireshark's search functionality to find packets containing `info_hash`. This showed many packets so I needed to filter further. Since we were looking for files downloaded by someone on our network, I focused on packets where the source address was from our local network `192.168.73.132` that contained `info_hash`.

```bah
bt-dht.bencoded.string contains info_hash and ip.src == 192.168.73.132
```
<img width="1541" height="892" alt="image" src="https://github.com/user-attachments/assets/35703e40-fa99-4b43-9956-12b32088d4ee" />

The filtered packets all contained the same `info_hash` value `e2467cbf021192c241367b892230dc1e05c0580e. This consistent hash across multiple packets indicated it was the main torrent our local host was downloading from. On googling, the hash corresponded to `ubuntu-19.10-desktop-amd64.iso`

Thus the flag for this challenge is `picoCTF{ubuntu-19.10-desktop-amd64.iso}`
