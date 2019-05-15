### **Linux Serial to USB Adapter Setup**

Install cu 
$ sudo apt-get install cu

Plug in the converter and change permissions
$ sudo chmod 777 /dev/ttyUSB0

To make the chmod persistent:
Run dmesg and note the adapter idVendor and idProduct
Create a file such as usbserial.rules in /etc/udev/rules.d  directory to load automatically.

$ sudo nano /etc/udev/rules.d/usbserial.rules
SUBSYSTEMS=="usb", ATTRS{idVendor}=="067b", ATTRS{idProduct}=="2303", GROUP="users", MODE="0666"
