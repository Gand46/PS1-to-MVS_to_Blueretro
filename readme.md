Forked from www.delta-island.com github an implementation of the code to use it with the mvs neogeo connecting it directrly to the pcb and consolize the MVS without to much pain only need 2 Arduino pro mini a ESP32 i already rewrite the pinout disposition to connect it more easy from the mvs board.

I will explain easy and short how make it:

1. Flash the arduino pro mini or mini (328p - 5v) for each player you will need one so the MVS support 2 players}
   * You can flash only one if you want but the advantage of use the PSX-MVS is that you only will need one ESP32 not two of it
2. Flash the Blueretro with the PSX/PS2 controller firmware (Use the blueretro tutorial for this https://github.com/darthcloud/BlueRetro/wiki/BlueRetro-DIY-Build-Instructions)
3. Go to the Web Config user manual from you PC (Blueretro.io) connect to the PS2XXXX blue retro and enter on the option "Advance config page" and enter to the option: "Global config" 


![Alt text](https://github.com/darthcloud/BlueRetro/wiki/img/web/advance_global.png)

4. on the System option change the (Default: Auto) to PSX, save and you are almost done
5. Connect the pinout from the Blueretro to the Arduino there are only 4 pins (the ACK Pin are not connected):

PLAYER 1

ESP32 - IO19 - DATA P1 - Arduino P1 Pin 12

ESP32 - IO32 - CMD P1 - Arduino P1 Pin 10

ESP32 - I34 - CS P1 - Arduino P1 Pin  5

ESP32 - IO33 - CLK P1 - Arduino P1 Pin 4

ESP32 - NC - ACK P1 - Arduino P1 Pin N/A (Not Connected)

PLAYER 2

ESP32 - IO22 - DATA P1 - Arduino P2 Pin 12

ESP32 - IO27 - CMD P1 - Arduino P2 Pin 10

ESP32 - IO5 - CS P1 - Arduino P2 Pin  5

ESP32 - IO26 - CLK P1 - Arduino P2 Pin 4

ESP32 - NC - ACK P1 - Arduino P2 Pin N/A (Not Connected)

6. Finally connect the arduino to the MVS using the mvs diagram of the NEOGEO



# PS1 to NEOGEO Controller repository
www.delta-island.com

This projet allow you to use playstation 1 controller (gamepad or joystick) on Neogeo AES or MVS
This projet is under GNU GENERAL PUBLIC LICENSE

You can build it by yourself for less than 15$ for MVS consolized- 
