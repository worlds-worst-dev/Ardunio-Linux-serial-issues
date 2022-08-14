# SOLUTION Ardunio-Linux-serial-issues
Solution to serial connection issue

OS - POP_OS 22.04

Arduino IDE - any

Issue Cannot access serial ports for communication to arduino device

Solution 

run ~$ sudo dmesg | grep tty

Output

[    0.130589] printk: console [tty0] enabled \
[    4.579410] usb 1-3: ch341-uart converter now attached to ttyUSB0 \
[    5.525219] usb 1-3: usbfs: interface 0 claimed by ch341 while 'brltty' sets config #1\
[    5.528334] ch341-uart ttyUSB0: ch341-uart converter now disconnected from ttyUSB0\
[  346.404799] usb 1-3: ch341-uart converter now attached to ttyUSB0\
[  347.000418] usb 1-3: usbfs: interface 0 claimed by ch341 while 'brltty' sets config #1\
[  347.003602] ch341-uart ttyUSB0: ch341-uart converter now disconnected from ttyUSB0\
[  852.812428] usb 1-3: ch341-uart converter now attached to ttyUSB0\
[  853.407050] usb 1-3: usbfs: interface 0 claimed by ch341 while 'brltty' sets config #1\
[  853.410528] ch341-uart ttyUSB0: ch341-uart converter now disconnected from ttyUSB0\
[  916.475972] usb 1-3: ch341-uart converter now attached to ttyUSB0\
[  917.071859] usb 1-3: usbfs: interface 0 claimed by ch341 while 'brltty' sets config #1\
[  917.075117] ch341-uart ttyUSB0: ch341-uart converter now disconnected from ttyUSB0\
[ 1185.160637] usb 1-3: ch341-uart converter now attached to ttyUSB0\
[ 1185.761065] usb 1-3: usbfs: interface 0 claimed by ch341 while 'brltty' sets config #1\
[ 1185.764291] ch341-uart ttyUSB0: ch341-uart converter now disconnected from ttyUSB0\
[ 1326.896107] usb 1-3: ch341-uart converter now attached to ttyUSB0\
[ 1327.497679] usb 1-3: usbfs: interface 0 claimed by ch341 while 'brltty' sets config #1\
[ 1327.500890] ch341-uart ttyUSB0: ch341-uart converter now disconnected from ttyUSB0\
[ 1656.771494] usb 1-3: ch341-uart converter now attached to ttyUSB0\

If the output contains 'britty' as seen in the output above remove the britty program (Unless you require braille) using the following command;
This is due to the britty service blocking the use of the serial port

sudo apt remove brltty

Serial communication for Arduino should now be good as gold!

