# Installing ElemintOS
Normally, the installation process would be straightforward, but I kinda messed up. So you have to follow this guide to install the OS correctly.

## Go through the elementaryOS Initial Setup
On the live ISO, you will be prompted to choose a language and keyboard layout, enter your username and password etc. Those will only last for the Live ISO. 

## Starting the Installer
After you finished, you notice that you will not be able to login due to LightDM then giving you the error "Session exited with code 1". To fix this, we need to switch to a console TTY (by pressing Ctrl + Alt + F#) and log in with the credentials you set during setup.
You will probably see something like this:
```
Linux Mint 21.2 Victoria (hostname) tty*
(hostname) login:
```

At this part, you will have to specify the **username** and **password** you entered during setup.
After that, run the `nmtui` tool to configure an internet connection (except if you have ethernet).
You will then have to run `sudo apt update`. In the 7.1 Horus-Victoria ISO, you will notice that when trying to update, APT will discover conflicts. To fix those, run `sudo apt remove nemo-preview xviewer xviewer-dbg` , and we will be able to continue by running a `sudo apt update` again.
We will then first have to install GNOME Shell temporarily to make the installer run, but first we need to add elementaryOS' PPA repository. To do this, run `sudo add-apt-repository ppa:elementary-os/stable` and confirm. Now we can finally proceed to installing the GNOME shell by running `sudo apt install gnome-shell`. After it's done, run `startx /bin/gnome-shell`. When you're in the GNOME Shell, open Activities, search for "Install" and open the Ubiquity installer for ElemintOS. The installation process is actually straightforward, so just follow the steps.

## Fixing LightDM after Installation
Congratulations! You finished installing ElemintOS! But you still get the same "Session exited with code 1" error. Not to worry, this is easy to fix. Navigate to a console TTY again, log in with the credentials you entered during the **installer**, and run `sudo apt update`. You may notice the same APT conflicts. To fix these again, run `sudo apt remove nemo-preview xviewer xviewer-dbg` . After that, you may now run `sudo apt install openbox` . Nothing else, just reboot. After rebooting, click on the gear icon next to the password field, select "Pantheon" and log in normally with the credentials. You're basically done with your system.

## Support
Issues? You can report them in:

- The "costmiku-bugs" Google Groups
- The Discord guild at the invite "3PRMhaBuuT"
- The matrix room #icycoide:envs.net

Thank you for installing ElemintOS, despite it being unstable as hell!