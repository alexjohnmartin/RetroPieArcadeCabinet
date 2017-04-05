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

   ![Configure controller](https://cloud.githubusercontent.com/assets/10035308/9140482/cf42f25c-3cee-11e5-8f91-c1fc1c57175c.png "RetroPie configre controller")

4. Installing ROMs; the easiest way to get ROMs on to the device is to use a USB flash drive. You need to create a folder on your flash drive called “retropie” (all lower-case), plug this into the Raspberry Pi while running RetroPie, wait for the flashing on the drive to stop, plug the drive back into your PC (you’ll notice that RetroPie has created a folder structure inside the /retropie folder), drop your ROMs into the correct folders on the flash drive, and plug it back into the Raspberry Pi while running RetroPie. RetroPie should recognise that there are ROMs and will copy them to the SD card. If you restart RetroPie you should see your games. __You do not need to keep the flash drive plugged in.__
5. Mapping buttons in RetroArch. When you first set up a controller, particularly if you’ve used an Xbox controller, you might find that the buttons are mapped the wrong way around in certain games. Nintendo games have A and B buttons the opposite way around than Xbox. You can alter the mappings of your buttons by going into the RetroArch config:

   ![RetroArch config](https://delightlylinux.files.wordpress.com/2016/02/rgui3.png "RetroArch config")

   Go into Input, select player 1, hit Bind All, go through all the different buttons, __and make sure you hit the SAVE option__ if your happy with the changes.

### Step 2 - Setting up the screen

Before putting everything into the cabinet I highly recommend plugging in the screen to your Pi and getting it set up. I followed the instructions here: https://learn.adafruit.com/adafruit-dpi-display-kippah-ttl-tft

#### Tips
- When plugging the ribbon from the screen into the driver board you need to CAREFULLY pull back the black plastic thing that’s sitting in the port – this should slide back about 2mm and leave enough space to insert the ribbon. You then push the black part back in to secure the ribbon. It is very easy to break this black part off if you are heavy handed. 

   ![TFT connector port](https://cdn-learn.adafruit.com/assets/assets/000/024/430/medium800/adafruit_products_connector.jpg?1428703283 "TFT connector port")

- Getting to Linux command prompt – to perform installation of the packages and to alter the linux config files to set up the screen you’re going to need to get to the command prompt. Plug in your USB keyboard and hit F4 to exit out of the RetroPie app (aka EmulationStation). If you want to get back into the main RetroPie interface from the command prompt you can just type “emulationstation”.

#### Flipping the screen

Once the screen is correctly installed and being used by Linux, for my case design you’re going to have to install the screen upside-down; i.e. we need to flip the screen in the config. 

From the command prompt run `sudo nano /boot/config.txt` then add `display_rotate=2` to the end of the file. Reboot and your display will be rotated 180 degrees.

### Step 3 - 3D printing the screen clamps

Print 4 copies of the [ScreenClamps.stl](ScreenClamp.stl) model.

### Step 4 - Assembling the cabinet

Laser cut the [Cabinet plans](Cabinet.svg) out of 6mm plywood. __If you use a different thickness of material the notching will not work.__

Glue the bottom, back, sides and top+bottom front panels in place. __DO NOT GLUE ON THE TOP!__ I recommend only putting a small dot of glue on the inside of each notch cutout. (TODO: image)

Chop 10 x 1" lengths of the 1/2" square wooden rod. Glue these inside the sides of the case so you can screw the control panel, screen panel and the small panel above the screen to them. (TODO: image)

Insert the buttons and joystick into the control panel; wire this to the USB adapter. (TODO: image)

Attach the screen to the back of the screen panel using the 3D printed clamps. Attach the display driver board to the ribbon cable. (TODO: image)

Attach the Pi to the board that goes above the screen using some PCB spacers. (TODO: image)

Insert the USB extensions into the holes in the case. (TODO: image)

Screw in the control panel. (TODO: image)

Glue in the board above the screen. (TODO: image)

Screw in the screen panel; plug the driver board on to the Pi. Plug in the USB cables. Place the top on. (TODO: image)

PLAY!

## Performance  

With a Raspberry Pi 2 inside I was able to play Nintendo SNES games well, N64 games ran but were unplayable.

A Raspberry Pi 3 plays N64 and Playstation 1 games nicely however you'll need an analog joystick to play these games (i.e. plug in a modern USB controller).