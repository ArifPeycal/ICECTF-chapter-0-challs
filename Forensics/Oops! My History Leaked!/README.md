# **Oops! My History Leaked!**

## Description

Uh-oh! Looks like our dear challenge author accidentally leaked his own Chrome browsing history...and, well, it’s interesting, to say the least. He swears he was just doing "research," but we're not so sure.

The flag was scattered in three parts.

## Solution

You can open SQLite database file using DB Viewer like this [SQLite Viewer Web App](https://sqliteviewer.app/). 

The flag is in base64 and will be hidden inside the URL in three parts. Sort by title to see all the URLs. 

![image](https://github.com/user-attachments/assets/c7c9f714-c926-489e-aa33-4e19ac3d54d5)

Use Cyberchef to decode the base64 string. 

![image](https://github.com/user-attachments/assets/5f298c8e-579f-4f6b-b843-69a1a3277dfd)

## Flag

ICECTF{y0ur_h1st0ry_1s_m1n3}
