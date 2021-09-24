# PterodactylArmInstalationGuide
how to install pterodactyl on arm devices (rasberry pi)


# Step 1 : install a 64 bit os:
 
  rasberry pi imager : https://www.raspberrypi.org/software/ 
  rasbian 64 bit Image : https://downloads.raspberrypi.org/raspios_arm64/images/raspios_arm64-2020-05-28/2020-05-27-raspios-buster-arm64.zip
  Launch Raspberry Pi Imager.
  Click Choose OS. ...
  Select an OS from the list.
  Click Choose SD card.
  Select from the list the SD card you want to write to.
  Click Write to begin the image writing process.

# Step 2 : Set a ssh Connection (optional) :
  
  Click the raspberry logo at the top-left corner.
  Select Preferences > Raspberry Pi Configuration.
  Navigate to the Interfaces tab in the configuration window.
  Enable SSH in the second line.
  Click OK to save the changes
  (and open Port 22 (https://www.hellotech.com/guide/for/how-to-port-forward))

# Step 3: Update tour system:
  
  $ sudo apt update
  $ sudo apt full-upgrade
  
# Step 4: Install Docker:
 
 $ curl -sSL https://get.docker.com/ | CHANNEL=stable bash
 
 If its dont work :
 
  # Docker Installation #2
$ sudo apt update
$ sudo apt install -y \
     apt-transport-https \
     ca-certificates \
     curl \
     gnupg2 \
     software-properties-common

 Get the Docker signing key for packages
curl -fsSL https://download.docker.com/linux/$(. /etc/os-release; echo "$ID")/gpg | sudo apt-key add -

 Add the Docker official repos
echo "deb [arch=$(dpkg --print-architecture)] https://download.docker.com/linux/$(. /etc/os-release; echo "$ID") \
     $(lsb_release -cs) stable" | \
    sudo tee /etc/apt/sources.list.d/docker.list

 Install Docker
$ sudo apt update
$ sudo apt install -y --no-install-recommends \
    docker-ce \
    cgroupfs-mount
    
Run Docker 
$ sudo systemctl enable docker

$ sudo systemctl start docker

