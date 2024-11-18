# **Music of the Spectrum**

## Description

I've been listening to my favorite song on repeat, but something feels… off. It sounds almost like the original, but there’s something in there that I can’t quite place. Maybe there is something hidden in the spectrum.

## Solution

When you open the `.wav` file, maybe you can recognize that it is a song from Coldplay titled A Sky Full of Stars ⭐. The song seems ordinary until timestamp `3:03 - 3:22`. There are some strange noises from the audio.

These noises are what we call **audio steganography**. It is a way to hide some texts or messages inside an audio file. To see the message, you need to use spectrogram analyzer software. 

### Option 1: Audacity (available on Windows, Linux, macOS).

Open the file inside Audacity and make sure to enable spectrogram wave. 

![image](https://github.com/user-attachments/assets/b29eb83f-61b3-4956-9658-7e8ac646aae9)

If you zoom on the timestamps, you can see the flag hidden in the audio. 

![image](https://github.com/user-attachments/assets/5b24fcae-17c1-4007-b8a9-771cfc32e242)

## Option 2: Online Spectrum Analyzer

If you don't want to install any software, there are bunch of online tools that you can use. 

1. https://academo.org/demos/spectrum-analyzer/
2. https://www.dcode.fr/spectral-analysis

![image](https://github.com/user-attachments/assets/b1ee7058-4e29-481c-8256-7556d36ecbfc)

## Flag

ICECTF{h1dden_1n_th3_fr3qu3nc13s}
