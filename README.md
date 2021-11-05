# gpio-driver
A Linux kernel driver for the Raspberry Pi. Allows user to toggle GPIO pins on/off by writing to a file in /proc/. This was written following this tutorial https://youtu.be/lWzFFusYg6g. I wrote this up for future reference.
### Instructions
Run 
```
make
```
```
sudo insmod lll-gpio-driver.ko
```
To test, hook up an LED (with current limiting resistor; or not if you are feeling dangerous) to GPIO 21 (bottom pin, left column, ground is bottom pin right column). Then try
```
echo "21,1" > /proc/lll-gpio
```
The LED should light up. If you run 
```
echo "21,0" > /proc/lll-gpio
```
it should turn off.

You can also try 
```
dmesg | grep "Data buffer"
```
to check that it's working.

To remove the driver, run
```
sudo rmmod lll_gpio_driver
```
