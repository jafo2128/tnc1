tnc1
====

Mobilinkd TNC1 Firmware

====
To build the software, just type "make".  The EEPROM section needs to be
removed from the ihex file.

avr-objcopy -O ihex -R.eeprom images/mobilinkd-tnc1.elf images/mobilinkd-tnc1.hex

The hex file can then be uploaded using "avrdude -c avr109" or using the
Mobilinkd Android configuration app.

The Mobilinkd TNC1 uses the XBoot++ bootloader:
https://github.com/alexforencich/xboot

To build an image which includes the bootloader, build the xboot++ bootloader
using the supplied xboot configuration file.  Then merge the two files with
srec_cat.

srec_cat xboot/xboot.hex -intel mobilinkd-tnc1/images/mobilinkd-tnc1.hex \
    -intel -o mobilinkd-tnc1/images/mobilinkd-boot.hex -intel

The output file, mobilinkd-boot.hex, can then be uploaded via the ISP port on
the board using an ISP programmer such as the USBASP v2.0.  This is the
programmer that I use, along with a custom cable with pogo pins.




Finally words from us Archivers and Developers.. 

##### Donate

People from time to time wish to donate a little money. Donating won't get you anything special, other than a warm feeling inside, and possibly urge me to produce more freely available material for interesting projects. You can donate via [PayPal](https://www.paypal.com), just click [donate](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=3PXVSLXFBS45E) button available below - it will redirect you to the secured PayPal page where you can provide donation amount (there is no minimal value). Any donations are apreciated greatly, and we thank you all in advance for your support along the ways..

[![Donate via PayPal](https://www.paypalobjects.com/en_US/GB/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=3PXVSLXFBS45E)



