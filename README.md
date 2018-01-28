# Savant-RaspberryPi-Relay-8
Savant control of 8 Raspberry Pi GPIO pins. Relays attached to these GPIOs can be used to control garage doors, outlets, sprinklers or any other on/off or momentary open/close device.
## Synopsis
The Savant profile reads and writes GPIO pin states to the Raspberry Pi using WiringPi (http://wiringpi.com).
The profile will read a pin's state whenever a write command is sent and will also poll for changes every 30 seconds. 
After login the profile sets the pins to output thus is not valid for contact sensing input applications. 
For sensing of input pin state changes use another Raspberry Pi and the Pi Sensor profile.
Communication is made with a telnet session and login credentials are defined with user variables on the device in Blueprint.
## Preparation
STEP 1: Install wiringPi on the Raspberry Pi that you are controlling.
Reference http://wiringpi.com/download-and-install/ for full instructions and usage.
```
cd ~
git clone git://git.drogon.net/wiringPi
```
```
cd ~/wiringPi
./build
```
```
gpio -v
gpio readall
```
STEP 2: Install telnet server
```
sudo apt-get install telnetd
```
STEP 3: Add profile to Blueprint Library then add to configuration.
