# Introduction
This is a quick project I developed with the Pineapple WiFi, and it should cover basic attacks such as packet sniffing, dns spoof, and phishing wifi portals.

# Requirements
For this project, you will need:
- Docker, for the web server
- A target device, that will connect to the Pineapple's open Wifi
- Hak5’s Pineapple Mark VII

And the following modules installed on the Pineapple
- HTTPeek
- Evil Portal
- DNS Spoof

# Setting up the Pineapple WiFi
For this project, we connect the WiFi Pineapple to a wireless network, some steps might be different if you are using a wired connection instead.

1. After plugging it to a power source, the pineapple will take a few minutes to start.
2. Wait for the default network (SSID: pineapple) to show up on the wireless network list.
3. Connect to it and, on your browser, go to `172.16.42.1:1471`.
4. Log in with default credentials `root:hak5pineapple`.

Now that you are in the management console, let's get a few configuration done, starting with *Settings* (cogwheel at the bottom left corner of the screen)
1. Go to the *General* tab and update the password.
2. Go to the *Networking* tab and scan for networks. Connect to a network that has internet access. The pineapple WiFi will route traffic to that network.
3. Go to the *WiFi* tab and create a Management Access Point. We will connect to this network when not using our target device.

Now, under the *PineAP Suite* (WiFi icon on the top left part of the screen), let's configure our Open WiFi
1. Go to the *Open AP* tab and change the network's name.
2. Go to the *Filtering* tab and add the MAC address of the target device. This is important to aovid unaware people from connecting to this insecure network.

Finally, under *Modules & Packages* (Puzzle piece icon on the left corner of the screen), let's install the modules and their dependencies.
1. Go to the *Modules* tab and install the following pakacges:
- HTTPeek
- Evil Portal
- DNS Spoof

You are done with the setup.