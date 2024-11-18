# **Inception**

## Description

"Downward Is The Only Way Forward."  -Dom Cobb-

You’re entering a world of layers within layers, like a dream within a dream. Somewhere deep inside this archive lies the final truth but only if you can make it to the core.

## Solution

You were given `dream.zip` that when extracted will contains another zip file `dream_0.zip`. Each zip will have similar contents, one text file that contains some numbers and another zip file. The pattern will continue until the end of files.

Let’s look at `dream_0.txt`. If you are familiar with PNG file format, you will automatically detect the file signature (`89 50 4E 47`). 

```bash
 89504e470d0a1a0a0000000d494844520000063c0000042e0806000000681894b2000000017352474200aece1ce90000000467414d410000b18f0bfc6105000000097048597300000ec400000ec401952b0e1b0000ffa549444154785eecfd07bcad5579ef7ddfb0694a53b1a2a222368a0d0b369af4a2
 [SNIPPED]
```

TLDR:

1. Extract every zip file inside this nested zip
2. Combine the contents of every `dream_{i}.txt` file into one file. 
3. Convert from hex to bytes and save the output file as `.png`.

## Option 1: Make Your Own Script

This requires a script to solve because it will take so much time to manually extract each file and copy each text content. Just let our friend ChatGPT to create a Python script for us. 

```python
import zipfile
import os

index = 0
output_file = "collected_dreams_hex.png"
starting_directory = os.getcwd()  

open(output_file, 'wb').close()

# Loop through the files until no zip file is found
while True:
    zip_filename = f"dream_{index}.zip"
    txt_filename = f"dream_{index}.txt"
    next_dir = f"dream_{index + 1}"

    # Check if the zip file exists in the current directory
    if not os.path.isfile(zip_filename):
        print("Reached the end or missing zip file:", zip_filename)
        break

    # Unzip the current zip file
    with zipfile.ZipFile(zip_filename, 'r') as zip_ref:
        zip_ref.extractall(next_dir)

    # Change to the extracted directory
    os.chdir(next_dir)
    print(f"Current directory: {os.getcwd()}")  # Print the current directory

    # Read the content of the txt file as bytes and convert from hex
    if os.path.isfile(txt_filename):
        with open(txt_filename, 'rb') as txt_file:
            content = txt_file.read()

        # Convert the hex string content back to bytes
        try:
            hex_content = content.decode('utf-8').strip()  # Decode to string (hex)
            byte_content = bytes.fromhex(hex_content)  # Convert the hex string to bytes
        except ValueError as e:
            print(f"Error converting hex to bytes in {txt_filename}: {e}")
            continue  # Skip this iteration if there's an error

        # Append the byte content to the output file
        with open(os.path.join(starting_directory, output_file), 'ab') as output:
            output.write(byte_content)  
    else:
        print(f"Warning: {txt_filename} not found in {next_dir}")

    index += 1

os.chdir(starting_directory)
print(f"Process completed. All hex content appended to {output_file} in {starting_directory}.")
```

The script will create a `.png` file and the flag will be on the bottom right of the image. 

![image](https://github.com/user-attachments/assets/6dcbc21f-831f-4190-9123-b5e1d4afa431)

## Option 2: CyberChef

If you have all contents of text files combined, you can use CyberChef to render the image. 

![image](https://github.com/user-attachments/assets/1ef369c4-f2f6-448a-9b66-320f3ec97672)

## Flag

ICECTF{h3x_byt3s_t0_im4g3}
