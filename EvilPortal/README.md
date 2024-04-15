# Get your files ready
This part of the project was based on (SgtFoose's evil portals)[https://github.com/SgtFoose/Evil-Portals].  
However, to get a better experience, I redirected the user to the actual mc donald's website, instead of the "Anauthorized login" page that comes by default. You can find all the updated files in the "" folder.  
1. Copy the files to the pineapple: `scp -r ./mcdonalds-login/ root@172.16.42.1:/root/portals/`.
2. Navigate to the evil portal module. If not showing on the left side of the screen, look for it under *Modules & Packages*.

# Starting Evil Portal
1. Find the portal you just added, should be "mcdonalds-login" and click on *Activate*. If you can't find the portal there, something probably went wrong copying the files.
2. Click on the *Start Web Server* and *Start*. *Enable on boot* is optional here.
3. Next time someone connects to this network, they will be prompted to authorize through that portal first.

