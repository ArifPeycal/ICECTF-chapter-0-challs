# **Magic Bytes**

## Description

A corrupt image file? Weird 🤔.

It seems like someone might have tampered with the file. I've heard there are specific bytes that help computers identify the file type. You might be able to fix it by restoring these correct bytes.

## Solution

The challenge description hinted towards certain bytes that we called “**file signature**” or “**magic bytes**”. These bytes are really important to determine the file types.

You can search on Google or use ChatGPT to determine JPEG magic numbers. 

JPEG Magic Bytes: `FF D8 FF E0 00 10 4A 46`

References: [List of file signatures - Wikipedia](https://en.wikipedia.org/wiki/List_of_file_signatures)

Open `.jpg` file using hex editor like [HexEd.it - Browser-based Online and Offline Hex Editing](https://hexed.it/).  You can see the bytes are wrong (`DE AD BE EF`). 

![image](https://github.com/user-attachments/assets/a9d871c7-ebcc-47b6-911a-ea8f130f7e50)

Change from `DE AD BE EF` to `FF D8 FF E0.` 

![image](https://github.com/user-attachments/assets/e0889628-b073-4a91-b014-9ac608888501)

And, you will get the fixed image.

![image](https://github.com/user-attachments/assets/a967893a-1875-4701-bea3-fa453d749396)

## Flag

ICECTF{kn0w_y0ur_m4g1c_byt3s}
