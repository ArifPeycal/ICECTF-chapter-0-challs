# **Secure Intern 2.0**

## Description

"Alright, new intern, I’m trusting you to develop a secure and encrypted website for our company," the boss directed. "Oh, and don’t forget—I’ll need a screenshot of the interface when it’s finished."

No problem. I’d been researching this one protocol that could make any website as secure as a fortress. This would be a breeze.

## Solution

You were given a `pcap` file to analyze. You can view the contents of the pcap file using **Protocol Hierarchy (`Statistics → Protocol Hierarchy`)**.  

From Protocol Hierarchy, we see some TLS packets and also HTTP packets. TLS packets indicate that the communications were encrypted. 

![image](https://github.com/user-attachments/assets/2aa2e090-7455-4877-99bc-b06dba09c5a9)

There are some HTTP packets that are not encrypted, so you can see the contents. Looks like someone is accessing multiple text files. You can see the text file contents by `Follow TCP Stream`. 

![image](https://github.com/user-attachments/assets/303cdb37-6abf-48eb-8006-a7856e19ea51)

All text files look similar, which are passwords for some software except for `key_log.txt`. 

![image](https://github.com/user-attachments/assets/4db762f7-355e-4bcf-bdcc-f44bf72bad3b)

If you are not familiar with the content, you can search or ask ChatGPT.
![image](https://github.com/user-attachments/assets/0f463668-1da8-43e7-bde7-8572a9880bca)


So, we can use key_log.txt to decrypt encrypted HTTP packets. First, we need to export key_log.txt file. From the **Wireshark menu**, go to `File` > `Export Objects` > `HTTP`. Save key_log.txt into any directory. 

![image](https://github.com/user-attachments/assets/50a0b1fd-400f-402f-9080-00b61fdb0531)

You can load it into Wireshark by going to:
`Edit` > `Preferences` > `Protocols` > `TLS` and then pointing to that file Wireshark to this file under (Pre)-Master-Secret log filename. 

When you revisit the Protocol Hierarchy, you’ll notice that the TLS packets are no longer visible. This indicates that all encrypted TLS packets have now been successfully decrypted.

![image](https://github.com/user-attachments/assets/98028d3f-ade7-4e1a-9fd4-80d5c42d4f19)

Follow TCP Stream No 4 and you will see HTML page for the company website. First part is in comment. 

![image](https://github.com/user-attachments/assets/a2ad40b5-a97d-4df3-97b1-4a6c9e496cde)

There is on PNG file that you can export. The image is corrupted so you need to repair it. 

TLDR:

1. Remove first 16 bytes (those bytes are for PDF, not PNG)
2. Fix PNG header (`89 53 55 53` → `89 50 4E 47`) 
3. Fix IHDR chunk (`4C 4D 41 4F` → `49 48 44 52`)
4. Fix IDAT chunk (`53 4B 42 44` → `49 44 41 54`)
5. Fix IEND chunk (`53 47 4D 41` → `49 45 4E 44`)
6. Fix IDAT data length (`00 00 00 0D` → `00 00 AA 13`)

Second part is under Software Devlopment segment. 

![image](https://github.com/user-attachments/assets/07e7589f-5e9f-4b41-b389-8fa1dd169872)

## Flag

ICECTF{3ncrypt3d_tr4ff1c_us1ng_ssl_tls}
