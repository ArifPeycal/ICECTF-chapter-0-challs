# **Lost in IOI**

## Description

Your friend is totally lost inside IOI City Mall Putrajaya since it’s her first time here, and she has no idea where she ended up! Take a look at your chat messages and piece together the clues to figure out where she is now. Good luck—she might just wander off again before you find her!

## Solution

You were given a screenshot of a chat between 2 persons.

![image](https://github.com/user-attachments/assets/f2ecc93d-d969-494e-90ab-2296485f742d)

We need to know where the last location of Syahirah, there are several information we can extract: 

1. She took an escalator from one of the parking zones
2. Saw a big grocery store
3. Saw a convenience shop with a green and blue logo on her left
4. She took another escalator, saw several designer shops
5. The shop she went sold handbags and it is Malaysian brand.

We know it is IOI City Mall but how to know its shops layout? Of course by using the mall directory. 

https://www.ioicitymall.com.my/?cat=128

IOI City Mall have 8 parking zones from A to H. Which parking zones would it be? We just need to check which escalator will bring the visitors to a grocery store. 

There will be 2 possibilities: 

1. Parking Zone C to Lotus
2. Parking Zone G to AEON

Still vague? Now, we can check if there is convenience shop with a green and blue logo nearby the grocery shops. 

There is no such shop near Lotus. But there is one shop near AEON. It is Family Mart. 

![image](https://github.com/user-attachments/assets/46a5f4d8-cc5d-4563-9866-b941f1fa0f22)

Take the escalator near Family Mart and you will see several designer shops on G Floor. There will be only one Malaysian brand shop which is Bonia.

![image](https://github.com/user-attachments/assets/e820f019-e6dd-479d-9840-b8a98c1790ee)

## Flag

ICECTF{Bonia}
