# KitchenSensors
This repo contains scripts to obtain data from sensors connected to a Raspberry Pi Zero.  In my case these sensors are located in the kitchen to help detect leaks under the kitchen sink but you're welcome to use the script however you need.

## Installing required components
To use this script you'll need an Adafruit DHT11 or DHT22 sensor along the Paho MQTT client.  These can be installed by:

```
sudo apt install python3-dev python3-pip
sudo python3 -m pip install --upgrade pip setuptools wheel
sudo pip3 install Adafruit_DHT paho-mqtt
```

## Acknowledgements
I've developed this script based on work by some fine individuals - their posts linked below.  Many thanks.

* https://pimylifeup.com/raspberry-pi-humidity-sensor-dht22/
* http://www.steves-internet-guide.com/into-mqtt-python-client/

## License
This project is subject to [the MIT License](LICENSE).
