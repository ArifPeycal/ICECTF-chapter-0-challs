# **Wireshark**

## Description

First time seeing a network capture file? Don't worry, there's nothing much in there other than the flag. You just need to know how to open the file.

## Solution

You need to install a packet analyzer software, like Wireshark to open `.pcap` file. 

In Wireshark, right-click any TCP packet, select **Follow > TCP Stream** to view the conversation.

![image](https://github.com/user-attachments/assets/a4f1cf18-3148-4f30-9162-c824a857b472)

Here’s the flag.

![image](https://github.com/user-attachments/assets/bc71c009-61e1-4228-ab2f-3296000f3fd0)

Also, you can check each of the packets since there are only 15 packets. But please learn how to filter in Wireshark so you don't need to check each packet. 

*P/S: Trust me, I had seen more than 10,000 packets for a CTF challenge, and it is a nightmare if you want to check it individually 💀.*

## Flag

ICECTF{p4ck37_5h4rk_dudUdu}
