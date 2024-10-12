# EspToPico
This is a converter board for an ESP32 to a Pi Pico for the purposes of the Sign Project.

The next revision of the board (3) should fix the following problems:
- It is impossible to program the board without resorting to using the bodged boot button. The official ESP32 dev board uses the serial chip to reset the ESP32 and put it in boot mode. Schematics are available online. This would be ideal.
- The button switch and LED lines had to be reversed here since the LED line was sent to an input-only pin. I reversed the labels for rev 2, but now there is a mismatch to the motherboard. This could be fixed later but it doesn't matter very much.
- The EEPROM MOSI, SCK, and CS lines are assigned to an input-only pin, rendering the EEPROM inaccessible. The ESP32 has enough storage to make this a non-issue, but it is still a problem. The easiest fix would be to switch the EEPROM MISO and MOSI lines then move the SCK and CS lines to regular GPIOs like GPIO 2 and 13.
