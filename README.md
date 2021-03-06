Patterned after the pimoroni/vl53l1x-python repository (https://github.com/pimoroni/vl53l1x-python.git)
# vl53l1x-python

Python library for the VL53L1X Laser Ranger.
Add TCA9548A support

# Installing

```
sudo pip install smbus2
sudo pip install vl53l1x
```

# Usage

```python
import VL53L1X

tof1 = VL53L1X.VL53L1X(i2c_bus=1, i2c_address=0x29)
tof2 = VL53L1X.VL53L1X(tca9548a_num=0, tca9548a_addr=0x70) # For TCA9548A
tof1.open() # Initialise the i2c bus and configure the sensor
tof2.open() # Initialise the i2c bus and configure the sensor
tof1.start_ranging(1) # Start ranging, 1 = Short Range, 2 = Medium Range, 3 = Long Range
tof2.start_ranging(1) # Start ranging, 1 = Short Range, 2 = Medium Range, 3 = Long Range
distance_in_mm1 = tof1.get_distance() # Grab the range in mm
distance_in_mm2 = tof2.get_distance() # Grab the range in mm
tof1.stop_ranging() # Stop ranging
tof2.stop_ranging() # Stop ranging
```
