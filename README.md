# snipsWebAdmin
Web based administrative system for Snips devices
Check out a short video on what this does and how to use it
https://youtu.be/gGwnzSOB9Nc


if installing this to a RPi make sure to run "sudo apt-get update" for the latest files

    #install pip
    sudo apt-get install python-pip python-git python-setuptools python-dev libffi-dev

    #update to the latest pip
    pip install --upgrade pip
    
    #clone this git
    git clone https://github.com/oziee/snipsWebAdmin.git
    
    #install deps
    cd snipsWebAdmin
    sudo pip install -r requirements.txt
    
# Starting web console


    #alter the settings.toml file in the base directory
    change the MQTT settings to match as needed
    
    #start
    ./boot.sh (good for using a service, also cleans up compiled pyc files for a fresh start)

    else you can just use 'python snipsFlask.py' 
    
    (if it doesnt start you need to change the boot.sh to bootable.. only have to do this once)
    chmod +x boot.sh
    
    then run ./boot.sh again
    
Or you can create a service to start the console when the pi starts

    #copy service file
    sudo cp snipsWebAdmin.service /lib/systemd/system/snipsWebAdmin.service
    sudo systemctl enable snipsWebAdmin.service
    sudo systemctl start snipsWebAdmin.service



