# **Wrong Format**

## Description

During an investigation, a suspicious file was found, but it seems that we didn't managed to open it. Our analysts suspect this file isn’t what it appears to be at first glance. Can you examine the file closely and uncover its true nature?

## Solution

This is a simple file analysis challenge. You need to know the real file format in order to see the flag. When you open the file as usual, it will give an error. 

You can check what file is this using `file` command in Linux. It is a PNG file disguising as PDF file.

```bash
file flag.pdf
flag.pdf: PNG image data, 1414 x 2000, 8-bit/color RGBA, non-interlaced
```

Or you can check the hex using hex editor. You can see PNG file header (`89 50 4E 47`), so you know this is a PNG file.

![image](https://github.com/user-attachments/assets/8b66195a-ec5b-41d0-b912-96b7a1a66a59)

Just change the extension from `.pdf` to `.png`

![image](https://github.com/user-attachments/assets/cbc1fd53-afa8-43e3-ae69-f1b9d2bb2d72)

## Flag

ICECTF{just_chang3_f1l3_ext3ns1on_r1ght?}

## Unintended Solution

LibreOffice in Linux can open the image as PDF file👀. This is faster but make sure you know about file format, ya.

![image](https://github.com/user-attachments/assets/17247a0b-ad40-46f0-8500-e84af6af5e4e)
