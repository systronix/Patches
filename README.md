# PATCHES FOR ARDUINO AND LIBRARIES
File descriptions follow
## Patches_1v6v9_TD1v29
Applies to: Arduino 1.6.9 and Teensyduino 1.29.
+ Serial2 patch to fix serial2_set_tx and _rx alternate pins
+ Apply to file arduino-1.6.9\hardware\teensy\avr\cores\teensy3 file serial2.c. A patched file is here for convenience.
+ Look for the function: serial2_set_tx (line 205)
+ Now look for the line(212): if ((SIM_SCGC4 & SIM_SCGC4_UART2)) {
+ Change UART2 to UART1.
+ Likewise in the set_rx function line 239. 
+ This patch is planned to be included in TD 1.30

See https://forum.pjrc.com/threads/32502-Serial2-Alternate-pins-26-and-31