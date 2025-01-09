# PS1_NEOGEO/MVS to BLUERETRO
Forked from www.delta-island.com | GitHub Repository: PS1-to-Neogeo-Adaptor  
This project implements the code to use an MVS NeoGeo by connecting directly to the PCB and consolizing the MVS with minimal effort. You will only need an Arduino Pro Mini/Mini (328p 5V) and an ESP32.  
## Key Changes:
**Pinout Disposition:** The pinout layout has been rewritten to simplify the connection to the MVS board.  
**Joystick Option Removed:** Modified the R1 button to function as button A instead of the (X) button when L1 + R1 + Select are held for a few seconds. This is useful for Metal Slug and some shoot 'em up games.  
**Added Coin Button:** The L1 button is now correctly used as the arcade coin button.  
## Steps to Implement  
### Flash the Arduino Pro Mini or Mini (328p - 5V):
Use the "[ps1_to_neogeo_ctrl_V1_MVS_CREDIT_FINAL.ino](https://github.com/Gand46/PS1-to-MVS_to_Blueretro/blob/master/Arduino%20Nano%20Code/ps1_to_neogeo_ctrl_V1_MVS_CREDIT_FINAL.ino)" remember that you will need the "Psx" Lib, you find it on [Arduino Nano Code/lib/Psx](https://github.com/Gand46/PS1-to-MVS_to_Blueretro/tree/master/Arduino%20Nano%20Code/lib/Psx)  

**Tutorial Arduino for flash pro mini:** https://docs.arduino.cc/retired/getting-started-guides/ArduinoProMini/  

>**NOTE:** You will need one Arduino per player, as the MVS supports two players, but also you can use only one if desired, but using the PSX-MVS_Blueretro allows for a single ESP32 instead of two on "Parallel 1P 5V (12 buttons) - Bluetretro" option.

### Flash the BlueRetro with PSX/PS2 Controller Firmware:

Follow the BlueRetro DIY Build Instructions for this step (https://github.com/darthcloud/BlueRetro/wiki/Flashing-firmware-Windows-10)

## Configure BlueRetro:
Access the web config  from your PC at blueretro.io. Connect to the BlueRetro via Bluethooth (will appear something like PS2XXXX) and navigate to the "Advanced Config Page".
and the "Global Config", in the System option, change the setting from "Default: Auto" to "PSX", click save button, and you are almost done.

![Alt text](https://github.com/darthcloud/BlueRetro/wiki/img/web/advance_global.png)

## Connect Pinout from BlueRetro to Arduino:
There are only 4 pins to connect for each arduino Player 1 and Player 2 ***The ACK pin is not connected***

**PLAYER 1:**
>ESP32 - IO19 - DATA P1 - Arduino P1 - Pin 12  
>ESP32 - IO32 - CMD P1 - Arduino P1 - Pin 10  
>ESP32 - I34 - CS P1 - Arduino P1 - Pin 5  
>ESP32 - IO33 - CLK P1 - Arduino P1 - Pin 4  
>ESP32 - NC - ACK P1 - Arduino P1 - Pin N/A (Not Connected)  


**PLAYER 2:**

>ESP32 - IO22 - DATA P1 - Arduino P2 - Pin 12  
>ESP32 - IO27 - CMD P1 - Arduino P2 - Pin 10  
>ESP32 - IO5 - CS P1 - Arduino P2 - Pin 5  
>ESP32 - IO26 - CLK P1 - Arduino P2 - Pin 4  
>ESP32 - NC - ACK P1 - Arduino P2 - Pin N/A (Not Connected)  


## Connect Arduino to MVS:

Use the MVS diagram of the NEOGEO to connect or solder it directly to the pads:

![Alt text](Images/BlueRetro_PSX_MVS_NEOGEO.png)

TODO: I am still exploring how to implement IGR (In-Game Reset) using a few buttons and a pin on the MVS cartridge reader.

# PS1 to NEOGEO Controller repository
www.delta-island.com

This projet allow you to use playstation 1 controller (gamepad or joystick) on Neogeo AES or MVS
This projet is under GNU GENERAL PUBLIC LICENSE

You can build it by yourself for less than 15$ for MVS consolized- 
