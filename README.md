This marks the beginning of my journey towards making a small audio receiver from scratch.
The receiver will utilise two TDA2030A amplifier chips, each amplifying their own respective channel.
For controlling and input switching, an ESP32 will be used.
This gives it the option for bluetooth connectivity through the ESP's bluetooth capabilities paired with the two built-in DAC pins (GPIO 25 and GPIO 26).
For high-quality digital audio an I2S bus with assigned pins for Data, Clock, and Word Select will be used.
The input selector will utilise an SSD1306 128x64 OLED display connected through an I2C-based connection, paired with buttons and a KY-040 rotary encoder to cycle through the menu, inputs and such.
On the 23rd of July the first proof-of-concept amplifier board has been designed.
It being a POC; it has regular conductive points for power as well as speaker terminals with a 2200uF filtering capacitor.
The schematic is provided in 'images/schematics/v0.1'. The first 3D render of the amplifier board is provided in 'images/renders/v0.1'.
