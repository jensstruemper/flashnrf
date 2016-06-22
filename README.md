# flashnrf.py utiliy
flashnrf.py is a utility script intended to auto flash hex files which are downloaded by the mbed online compiler to a nordic nrf51/52 MCU. The main reason to put this script together is that the nrf51-DK's mass-storage programming isn't working reliably on MAC OSX. Also manually dragging and dropping the downloaded hex-files isn't convenient.  

Flashnrf makes use of the watchdog python library to identify newly downloaded hex files and Nordic's pynrfjprog python library to flash the hex-file to the MCU.

## Installation:
1. Install watchdog
   `pip install watchdog`
2. Download & install pynrfjprog command line tools and python bindings from here:
  [Nordic nrf51 download area](https://www.nordicsemi.com/eng/Products/Bluetooth-low-energy2/nRF51822)
3. Clone or download flashnrf.py

## Usage:
1. Execute flashnrf.py from the directory you want to monitor `python flashnrf.py`
2. Trigger a compilation on the mbed online compiler and wait for the flash process to complete.

## Notes:
The script won't work out of the box when a hex-file is manually copied into the "monitored" directory as only file move and no file create actions are monitored. This is due to the common browser file download behavior where a temporary file is created first and moved to it's final name afterwards. 
