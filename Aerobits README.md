The Aerobits Aero/Aero Pro uses a JST GH 6 pin connector to communicate via UART. AS of now Stratux will only recognize the device when connected via USB. For this reason a Serial to USB bridge is required. Editing the Product Id and Vendor Id in the following file is required to make it work: https://github.com/GabrielN2002/stratux/blob/9fc1dc51e42a40928e1ccec339c86bd6a3eae2ac/image/99-uavionix.rules#L9
To determine your  Product Id and Vendor Id, SSH to your Raspberry Pi and run the lsusb command to get a list of connected USB devices. 

The  Product Id and Vendor Id cannot be the same as the one in the PingUSB: https://github.com/GabrielN2002/stratux/blob/9fc1dc51e42a40928e1ccec339c86bd6a3eae2ac/image/99-uavionix.rules#L12
If they are the same, the Aero/Aero Pro will not be recognized. A quick solution would be to change the FTDI Product Id from 6015 to 6014 using FT_Prog on a windows computer. (This only applies to FTDI FT231XS) 

Disclaimer: ONLY for experienced users. Changing the Product Id in FT_Prog to other than the suggested 6014 Product Id may result in your device being rendered useless. If possible it is better to avoid using the FTDI FT231XS.
