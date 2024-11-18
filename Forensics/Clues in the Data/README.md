# Clues in the Data
## Description

Our forensics division has uncovered the last photo taken at the scene of a crime. This image holds crucial clues about the suspect. Can you find out who took the picture and reveal the criminal’s identity before they vanish into the shadows? We’re certain the suspect's information, along with the date the image was captured, is still hidden within the photo.

## **Solution**

You’ve got a JPEG image of an airport, but there’s no flag visible in the picture. Bummer, right? But don’t worry, there’s still hope! If the description mentions finding out who took the picture and a date, it’s hinting at “**metadata**”.

Here’s what you do:

- Grab the image and head over to a metadata viewer (there are plenty online). One tool that’s pretty famous is Aperisolve.
- Upload the image, and just check out the ExifTool.
- Scroll through and look for OwnerName.

![image](https://github.com/user-attachments/assets/4fe60ee6-eb40-4390-bc6d-7be6a8fa111a)

## Flag

ICECTF{ex1f_d3tect1v3}

## Unintended Solution

You can use `strings`and `findstr`(Command Prompt) / `grep`(Linux Bash). You didn't even have to open the picture; this is how you get that **first blood** 🩸.

```bash
strings airport.jpg | findstr "ICE"
You can use Aperisolve to solve this question.ICECTF{ex1f_d3tect1v3}
```
