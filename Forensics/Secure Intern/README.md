# **Secure Intern**

## Description

"Hey, you—the new intern! I need you to secure these spreadsheets; it’s highly confidential," said the boss. Of course, I knew exactly what to do. Luckily, I remembered how to protect files with a password. It’s gotta be something easy to remember, just in case I forget.

I set the password and locked it up tight.  I even hide the flag inside those sheets. *Haha, no one’s gonna access this file except for me now!*

## Solution

You were given a `xlsx` file that was password-protected. The only hint of the password was that the password is something easy to remember, which usually not so secure. 

If there is no password provided in the challenge, we can try to crack the password using a tool called “**John the Ripper”**. John allows us to crack passwords from various software or programs like Zip archive, Microsoft Office software and PDF.

https://github.com/openwall/john

To crack password-protected Excel file, you can use this command:

```bash
office2john Employee_Data.xlsx > hash.txt 
john hash.txt --wordlist=/usr/share/wordlists/dirbuster/rockyou.txt
```

By running the command, we get the password as “**icecream**”. Thats why it is important to have a strong password that harder to crack.

![image](https://github.com/user-attachments/assets/f44abdf1-7aa4-4be2-a407-a87e4e5aece9)

Input the password and you can see many records in the spreadsheet. First part of the flag can be easily found using **Find and Replace** (`Ctrl + F`). 

![image](https://github.com/user-attachments/assets/8044dc0a-defc-4997-880f-a7d38628b4fd)

If you pay attention to the description, it is mentioned that the flag is hidden inside “sheets”, which means there is another sheet other than “**Data**” sheet. You can unhidden other sheet by right-click on **Data** sheet and click **Unhide**. You can see there is another sheet called **Flags**. 

![image](https://github.com/user-attachments/assets/05b0faf9-b186-4754-82a1-8389cade4fa8)

There are some country flags, but the flag we want to search is hidden from the plain sight. Like the first part, you can use **Find and Replace** to find the second part. 

![image](https://github.com/user-attachments/assets/98f3be82-ac0e-44fc-83a3-c6cd85904489)

## Flag

ICECTF{why_s34rch_f0r_p4ssw0rd_wh3n_y0u_c4n_cr4ck_1t?}
