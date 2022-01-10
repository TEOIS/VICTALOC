# VICTALOC
Concept behind VICTALOC is simple, just like we host phishing pages to get credentials why not host a fake page that requests your location like many popular location based websites. Read more on .VICTALOC Hosts a fake website which asks for Location Permission and if the target allows it, we can get :

* Longitude

* Latitude

* Accuracy

* Altitude - Not always available

* Direction - Only available if user is moving

* Speed - Only available if user is moving

Along with Location Information we also get **Device Information** without any permissions :

* Unique ID using Canvas Fingerprinting

* Device Model - Not always available

* Operating System

* Platform

* Number of CPU Cores - Approximate Results

* Amount of RAM - Approximate Results

* Screen Resolution

* GPU information

* Browser Name and Version

* Public IP Address

* Local IP Address

* Local Port

**Automatic IP Address Reconnaissance** is performed after the above information is received.

**This tool is a Proof of Concept and is for Educational Purposes Only, Seeker shows what data a malicious website can gather about you and your devices and why you should not click on random links and allow critical permissions such as Location etc.**

## How is this Different from IP GeoLocation

* Other tools and services offer IP Geolocation which is NOT accurate at all and does not give location of the target instead it is the approximate location of the ISP.

* Seeker uses HTML API and gets Location Permission and then grabs Longitude and Latitude using GPS Hardware which is present in the device, so Seeker works best with Smartphones, if the GPS Hardware is not present, such as on a Laptop, Seeker fallbacks to IP Geolocation or it will look for Cached Coordinates.  

* Generally if a user accepts location permsission, Accuracy of the information recieved is **accurate to approximately 30 meters**

* Accuracy depends on multiple factors which you may or may not control such as :

  * Device - Won't work on laptops or phones which have broken GPS

  * Browser - Some browsers block javascripts

  * GPS Calibration - If GPS is not calibrated you may get inaccurate results and this is very common

## Templates

Available Templates : 

* NearYou

* Google Drive (Suggested by @CRYPTOCOURSE)

* WhatsApp (Suggested by @INFOSEC)

* Telegram

## Tested On :

* Kali Linux

* BlackArch Linux

* Ubuntu

* Kali Nethunter

* Termux

* Parrot OS

* OSX - Monterey v.12.0.1

## Installation

### Kali Linux / Ubuntu / Parrot OS

```bash

git clone https://github.com/anynomouscheetah/VICTALOC.git

cd VICTALOC/

apt update

apt install python3 python3-pip php

pip3 install requests

```

### BlackArch Linux

```bash

pacman -S VICTALOC

```

### Termux

```bash

git clone https://github.com/anynomouscheetah/VICTALOC.git

cd VICTALOC/

pkg update

pkg install python php

pip3 install requests

```

### Docker

```bash

docker pull anynomouscheetah/VICTALOC

```

### OSX

```bash

git clone https://github.com/anynomouscheetah/VICTALOC

cd VICTALOC/

python3 victaloc.py

````

In order to run in tunnel mode, install ngrok by running this command in the terminal:

```bash

brew install ngrok/ngrok/ngrok

ngrok http 8080

````

## Usage

```bash

python3 victaloc.py -h

usage: victaloc.py [-h] [-s SUBDOMAIN]

optional arguments:

  -h, --help            show this help message and exit

  -k KML, --kml         Provide KML Filename ( Optional )

  -p PORT, --port       Port for Web Server [ Default : 8080 ]

  -t TUNNEL, --tunnel   Specify Tunnel Mode [ Available : manual ]

##################

# Usage Examples #

##################

# Step 1 : In first terminal

$ python3 victaloc.py -t manual

# Step 2 : In second terminal start a tunnel service such as ngrok

$ ./ngrok http 8080

###########

# Options #

###########

# Ouput KML File for Google Earth

$ python3 victaloc.py -t manual -k <filename>

# Use Custom Port

$ python3 victaloc.py -t manual -p 1337

$ ./ngrok http 1337
This tool has been created by Bilal Ali Cyber Security Expert and youngest certified ethical hacker of Pakistan...
