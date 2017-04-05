# Retro-Pie Arcade Cabinet

![Mini RetroPie arcade cabinet](https://raw.githubusercontent.com/alexjohnmartin/RetroPieArcadeCabinet/master/pics/IMG_20170318_184910.jpg "Complete cabinet")


## Notes
This guide goes through creating a miniature arcade machine using plug-and-play parts; no soldering was necessary, and only the most basic wood-working is needed. You need access to a 3D printer and laser cutter to make parts for the cabinet. 
If you only want help setting up RetroPie emulation on a Raspberry Pi just go through step 1 in the Build Steps.
Legal: You should only download and play ROMs of games that you own (i.e. have bought the physical cartridge or disks for).


## Parts
- Pi 2 or 3 - $40 - https://www.adafruit.com/products/3055
- SD card (4GB or bigger, class 10 for best performance)
- 7” screen - $37.50 - https://www.adafruit.com/products/2353 
- Screen hat - $14 - https://www.adafruit.com/products/2454 
- Arcade controls - $35 - https://www.amazon.ca/XCSOURCE-Encoder-Joystick-Fighting-AC426/dp/B01IQTN328/ref=sr_1_4?ie=UTF8&qid=1490645423&sr=8-4&keywords=arcade+buttons 
- Cables (optional) - $15 + $15 + $7
  - https://www.amazon.ca/gp/product/B01MU9LCCX/ref=oh_aui_detailpage_o05_s00?ie=UTF8&psc=1
  - https://www.amazon.ca/gp/product/B01MR4W6KE/ref=oh_aui_detailpage_o05_s00?ie=UTF8&psc=1
  - https://www.amazon.ca/gp/product/B002ZKNRMQ/ref=oh_aui_detailpage_o05_s00?ie=UTF8&psc=1 
- 6mm birch plywood
- 1/2" square wooden rod
- Short wood screws
- PCB spacers
- HDMI TV or monitor (for set up) 
- USB keyboard (for set up)
- Network cable (for set up)
- USB flash drive (for transferring ROMs to the Pi)
- USB game controller (for set up – not essential but useful - I used an Xbox One controller)


## Build steps

### Step 1 - Install RetroPie

I basically followed the steps listed here: https://retropie.org.uk/docs/First-Installation/

It boils down to: 
1. Put Rasbian image on SD card
  1. Download the image from here: https://github.com/RetroPie/RetroPie-Setup/releases/download/4.2/retropie-4.2-rpi2_rpi3.img.gz
  2. Unzip the download (I used 7zip on Windows): http://www.7-zip.org/download.html
  3. Download, install and run Win32DiskImager, use this to put the image onto an SD card: https://sourceforge.net/projects/win32diskimager/
2. Plug into TV with HDMI, USB keyboard and mouse, plug in SD card, Power with micro USB cable
3. Configuring a controller – if your Pi is all set up, after the system has booted you should now be asked to set up a game controller; you’ll cycle through all the buttons/joysticks on your controller and the correct mappings will be set up for you. __If you are prompted to press a button that does not exist on your controller you can just press and hold any button that you do have to skip forward.__
