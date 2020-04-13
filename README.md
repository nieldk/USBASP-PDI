# USBASP-PDI
Modified USBASP to work as a PDI Programmer

In order to use a cheap Chinese USBASP as a PDI programmer, a few modifications are neccessary.

## Instructions:
```
1. Clone this repository
   $ git clone https://github.com/nieldk/USBASP-PDI

2. Change to usb source directory
   $ cd usbasp.2011-05-28/firmware
   
3. Patch sourcesfile: http://sz.toyspring.com/usbasp-pdi-usbaspfirmware-20120816.diff
   $ patch usbasp-pdi-usbaspfirmware-20120816.diff

4. create the firmeare
   $ make main.hex
   
5. Apply the final, patched firmware to the usbasp
   $ avrdude -c usbasp -p atmega8 -U flash:w:main.hex
```
The device is now ready to use, but, in order to utilize the new PDI interface, you need to create a cable, as per this image.

![USBASP-PDI](/images/usbasp_pdi.png)

Here is my final result

![USBASP-PDI](/images/final.jpeg)

Note on drivers
On Linux and MacOS X no kernel driver is needed. Windows requires a driver for USBasp. Please use Zadiag tool to install this driver on Windows: http://zadig.akeo.ie/
