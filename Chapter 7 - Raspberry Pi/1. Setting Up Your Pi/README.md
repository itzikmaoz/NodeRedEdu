# Setting Up Your Raspberry Pi

This module will explain how to set up your Raspberry Pi, flash the image onto your microSD card and establish your connection with a static IP address. 

Video length: 4:57 minutes

### ![Link to Video](https://youtu.be/Yw_Em8w9KCk)

### Materials Required
- Raspberry Pi
- MicroUSB cord 
- Ethernet cable
- Ethernet to USB adapter (You need this if you don't have an ethernet port on your computer)
- MicroSD card (I am using a 16GB card. It is recommended to use a card over 4GB.)

### Instructions
1. First, we need to flash the Raspbian image onto your Pi's microSD card. 
2. Go to https://www.raspberrypi.org/downloads/raspbian and download the "Raspbian Jessie With Desktop" zip file. 
3. After downloading, double click on the file to unzip it and get the image file. The image file will have a .img extension.
4. Open a new terminal and type the command: 

``` javascript
diskutil list
```

  - This will enable us to find the path to the card

5. Find where your card is and copy down the path, usually it is at disk2. 
6. Unmount the card using this command

``` javascript
diskutil unmount /path/to/card
or 
diskutil unmountDisk /dev/disk2
```

7. Now, we are going to flash the image onto the card with the command:

``` javascript
sudo dd bs=1m if=~/path/to/img of=/path/to/card
sudo dd bs=1m if=~/Desktop/RASPBIAN/2017-07-05-raspbian-jessie.img of=/dev/disk2 /* The command I used */
``` 

- This command will take some time (sometimes over 15 minutes), so be patient while it is flashing the image. 
- After the flashing, we are now going to setup the Raspberry Pi with a static IP address. 

8. Plug your card into your Raspberry Pi, connect the Pi to power and internet via the ethernet cord. 
9. Open System Preferences > Network. 
10. Click on the USB tab in the left panel. 
11. Either select "Using DHCP with manual address" and assign the IP manually or select "Using DHCP" and copy down the IP address given. 
12. Remove the microSD card from the Pi and plug it back into your computer. 
13. Open the files on the microSD card (boot) and open the cmdline.txt file.
14. Delete all the text after the word "rootwait".
15. After "rootwait" type ip= and paste the Ethernet to USB IP address that you just copied and increment the number by one. 
- Ex. If the IP address is 169.254.63.86, change it to 169.254.63.87

16. Save the file and close it. 
17. Create a new file on the card, name it "ssh" and type in whatever you want in the file. 
- The latest version of Raspbian does not initialize a ssh shell, so this file will do that for you. 
18. Save the ssh file, close it and eject the card from the computer. 
19. Plug the card back into your Pi and power it on.
20. To test the connection to the Pi, open a new terminal and type: 

``` javascript
ping 169.254.63.86 (your IP address)
```

- If you receive messages back like this: "64 bytes from 169.254.63.86: icmp_seq=0 ttl=255 time=0.080 ms", then your connection is correct and you are ready to ssh into your Pi! 
- If you are getting a message similar to: "Request timeout for icmp_seq 0" then go back, check your connection, re-flash your image and check your IP addresses. 

21. To log onto your Pi, type:

``` javascript
ssh pi@your_IP_address
ssh pi@169.254.63.87 /* example */
```

22. Type in your password, the default is "raspberry" and now you are on your Pi! 

** Note: Make sure to change your Raspberry Pi's password for security purposes. Since every Pi is given this first password, you could be easily hacked. To change your password, type in the command: 

``` javascript
passwd
```
![Next module: Working With a Sense Hat >>](../Chapter%207%20-%20Raspberry%20Pi/2.%20SenseHat)
