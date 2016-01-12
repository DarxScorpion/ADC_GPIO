# ADC_GPIO
ADC reading and digital outputs on c

To run the program we just need to enable de BeagleBone Black ADC:

echo cape-bone-iio > /sys/devices/bone_capemgr.*/slots

The GPIO's are exported inside the adc_ogpios.c code

