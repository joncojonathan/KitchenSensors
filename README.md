# KitchenSensors
This repo contains scripts to obtain data from sensors connected to a Raspberry Pi Zero.  In my case these sensors are located in the kitchen to help detect leaks under the kitchen sink but you're welcome to use the script however you need.

Note this script has not been tested with Python 2, only Python 3.

## Obtaining the code
After installing Raspberry Pi OS on your hardware, or deciding to use another device, clone this repository on to your system:

`$ git clone git@github.com:joncojonathan/KitchenSensors.git`

## Installing required components
To use this script you'll need an Adafruit DHT11 or DHT22 sensor along the Paho MQTT client.  These can be installed by:

```
sudo apt install python3-dev python3-pip
sudo python3 -m pip install --upgrade pip setuptools wheel
sudo pip3 install Adafruit_DHT paho-mqtt
```

## Running on schedule
Use `cron` to run the script on boot and then to run every 5 minutes.  Edit your user's crontab via `crontab -e` then add:

```
@reboot python3 /home/pi/kitchenSensors/humidityTemperature_mqtt.py
*/5 * * * * python3 /home/pi/kitchenSensors/humidityTemperature_mqtt.py
```

If crontab has opened in `nano` you can save your file with `Ctrl + O` and then exit with `Ctrl + X`.  You should then see a message that says `crontab: installing new crontab`.

You can change the frequency run every X minutes by writing `*/X` where X is less than 60.  Note that the DHT11 and DHT22 can only take a reading every 2 seconds.

## Acknowledgements
I've developed this script based on work by some fine individuals - their posts linked below.  Many thanks.

* https://pimylifeup.com/raspberry-pi-humidity-sensor-dht22/
* http://www.steves-internet-guide.com/into-mqtt-python-client/

## License
This project is subject to [the MIT License](LICENSE).
