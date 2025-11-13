# Workstones
#### Turning aging devices into runable systems with PeppermintOS (FL-Devuan) & Kubuntu!
---
&nbsp;&nbsp; **Go through this list of actions to restore & return any computer capable of holding Linux 22 -> Linux 16 or Linux 24+. This is a very generic method for using Live-USB thumbsticks to do the inital work. This is my personal method for restoring locked, old and aged out devices to give them hope once again. You'll plug in one thumbstick with PeppermintOS and restore the hardware with a Linux wash. Then You'll rinse-in or wash-over with Kubuntu. Configure, BOOM, ready & on linux! </br></br>&nbsp;&nbsp;&nbsp;   A great way to take a "dieing machine" and reuse it for the "home".** </br></br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   **&nbsp; &nbsp; &nbsp; ;}** </br>
 
</br><hr></br></br>

## Get the ISOs  

 - &nbsp;&nbsp; I'm using <a href="https://peppermintos.com/download-and-install/" target="_blank" rel="noopener noreferrer">PeppermintOS [Devuan]</a> to restore the machine but you can pick any ISO you'd like but you'll have to change the commands to meet your ISO type/version.
  
 - &nbsp;&nbsp; I'm using <a href="https://kubuntu.org/download/" target="_blank" rel="noopener noreferrer">Kubuntu</a> as a main OS for the machine but you can pick any ISO you'd like but you'll have to change the commands to meet your ISO type/version.

</br></br>

## Rufie the USBs
&nbsp;&nbsp;&nbsp; I'm using <a href="https://rufus.ie/en/" target="_blank" rel="noopener noreferrer">Rufus [4.5+]</a> because I'm using a version of Linux greater than versions 18 & 20. Most versions of Linux (especially Ubuntu Flavors & Debain Flavors) changed when MBR became the common Partition scheme for UEFI booting. YUMI, UUI, UnetBootin or most versions of Ventoy based ISO installers/burners don't work with UEFI + MBR over secureBOOT. So, if you want a multiboot in the quick-n-easy way (ventoy based installers), you'll most likely have to turn off secure boot & you may not get the "DisplayLink" drivers to work properly without secureBOOT. Luckily most Linux distros 22 and newer will be able to handle more display drivers then ever before so many people won't need DisplayLink Drivers if they are using a Linux version greater then 20 (so 22, 24 and higher).


</br></br>

### Restore the Device with Peppermint OS (FL-Devuan)

&nbsp;&nbsp;&nbsp; When the system is off, insert the thumbstick Rufie'd with Peppermint OS (so a Peppermint Rufied Thumbstick) then turn on the device hitting ESC, F2, F10, F12, DEL or which ever option is needed for you to change your boot menu or enter BIOS. Change the boot menu to have the USB load first; then save and exit BIOS to begin installing the LIVE version of Peppermint OS. Normally if your are restoring a device you'll want to wipe the entire harddrive and start anew but there's a chance someone will need to use a different install option. Just ensure to use the fully loaded install method for all optional drivers (if there is a radio button for that).

</br>

### Rinse/Wash with Kubuntu

&nbsp;&nbsp;&nbsp; When the system is off, insert the Kunumtu Rufied Thumbstick then turn on the device hitting ESC, F2, F10, F12, DEL or which ever option is needed for you to change your boot menu or enter BIOS. Change the boot menu to have the USB load first (it may have changed since installing PeppermintOS); then save and exit BIOS to begin installing the LIVE version of Kubuntu. Normally here you'll want to wipe the entire harddrive (aka washing over) and start anew but there's a chance someone will need to use a different install option like to install along-side the PeppermintOS/other-Possible-OSs on the same drive (aka rinsing). Just ensure to use the fully loaded install method for all optional drivers (there should be an option for this).
  
</br><hr></br>

## Prepare your Machine

</br></br>

### Connect the Universe

&nbsp;&nbsp; Visit: <a href="https://itsfoss.com/mount-exfat/" target="_blank" rel="noopener noreferrer">itsFOSS.com/mount-exFAT</a> for the following commands to connect to the universe for mounting & using exFAT drives (normally Hard-Drives [HDDs]).

<code>sudo add-apt-repository universe</code>

<code>sudo apt update</code>

<code>sudo apt install exfat-fuse</code>

<code>sudo apt install exfat-fuse exfat-utils</code>
 </br>&nbsp;&nbsp; **this last one is intended for Lunix distros 20 and under but some odd flavors will need this**

 
</br></br>


### Drive the Displays
&nbsp;&nbsp;&nbsp; I use multiple displays and I use a J5create display adapter that uses MST instead of MCT. Kubuntu 22 & 24 has drivers for even my digital billboard monitor (ACER #P237HL). So, I don't need these drivers to run my displays but you may need these for your setup if you notice displays not running.

&nbsp;&nbsp;&nbsp;&nbsp; Download the packet: <a href="https://www.synaptics.com/products/displaylink-graphics/downloads/ubuntu" target="_blank" rel="noopener noreferrer">www.synaptics.com/products/displaylink-graphics/downloads/ubuntu</a> (look down for the buttons).

&nbsp;&nbsp;&nbsp;&nbsp; Visit: <a href="https://support.displaylink.com/knowledgebase/articles/684649" target="_blank" rel="noopener noreferrer">support.displaylink.com/knowledgebase/articles/684649</a> for the following commands to get generic <b><i>DisplayLink</i></b> display drivers.

<code>sudo apt-get update</code>

<code>sudo apt-get dist-upgrade</code>

**&nbsp;&nbsp; You will need to extract the zip files to where you can change-directory ("cd" command in the terminal) to the location. While in the file explorer, right click on the ".run" file, click properties and go through the settings to allow executable (may say "is exacutable"). Back in the terminal, change-directory into the location. Possible location could be: <code>cd ./Downloads</code>. Then run the file with this: <code>sudo ./displaylink-driver-xxxxx.run</code> but use the driver numbers (with dots/dashes/hyphens) instead of the x's before ".run".**

***NOTE:** &nbsp;&nbsp; This will cause a SecureBoot and some changes before this secure boot may be lost (mostly theme related changes). The system will tell you it's about to secure boot and you'll have to use your keyboard arrow keys and enter key for these type of popup menu. It'll then ask for a password, this is only going to be used for confirming you asked to install this driver set. This will not become a password for the linux or device. Again, this password is only for confirming the secure boot upon the next bootup. The system will ask you if you want to restart, let it reboot.*

</br></br>

#### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;You may need to readjust your boot settings during this reboot

</br></br>

**&nbsp;&nbsp;&nbsp;&nbsp; Once in the secure boot menu (a sometimes small blue box on the screen). You'll need to click "Enroll MOK" (should be the first option) then "Enroll" or "Approve" (sometimes it'll say enroll then ask if it's okay or cancel). Then finally let the system reboot again. It should reboot back into linux.**

***NOTE:** &nbsp;&nbsp;&nbsp;&nbsp; If your system doesn't drop into secure boot and you didn't obtain errors in the terminal, you probably don't need these drivers. Just continue as normal.*

</br><hr></br></br>

### Install the Apps
&nbsp;&nbsp;&nbsp; We are going to install a bunch of applications and programs to either setup for later or for standard use. Install these in order shown and skip any application you'd like to not have installed. The choosen apps for this section are for various reasons including making this OS more productive capable or to install repos you may need for something else. ***A quick tip:** most times you can just hit "up arrow" key to show the last input, delete the app name, put the next app name in and hit "Enter" key, then end with a confirm "y" then "Enter" key to just install one after the other.*

<hr></br>

#### Production Apps

<code>sudo apt-get install vlc</code> # Media Player

<code>sudo apt-get install obs-studio</code> # Broadcasting/Streaming Soft

</br></br>
#### Browser Apps

<code>sudo apt install librewolf</code> # Hardened Firefox

<code>sudo add-apt-repository ppa:xtradeb/apps</code> # Chrom Libraries [ungoogled edition]

<code>sudo apt update</code> # Normal Update Files Request

<code>sudo apt install ungoogled-chromium</code> # Installs Ungoogled Chromium

<code>ungoogled-chromium</code> # Runs Ungoogled Chromium

</br></br>
#### Draw/Art Apps

<code>sudo apt-get install blender</code> # 3D Manipulation Editor

<code>sudo apt-get install inkscape</code> # Rich Image Editor

<code>sudo apt-get install gimp</code> # Common Image Editor

</br></br>
#### Video-Editing Apps

<code>sudo apt-get install kdenlive</code> # Video Editor

<code>sudo apt-get install shotcut</code> # Video Editor

</br></br>
#### Game Running Apps

<code>sudo apt-get install lutris</code> # Multi-System Game HUB & Driver/Installer

<code>sudo apt-get install winehq-devel</code> # Run Windows Stuff on Linux

<code>sudo apt install software-properties-common apt-transport-https curl -y</code> # Prerequisit for Steam

<code>sudo apt install steam-installer steam-devices</code> # Steam by Valve for Games on most systems

</br></br>
#### Audio & Synth Apps

<code>sudo apt-get install audacity</code> # Audio

&nbsp;&nbsp; Visit: <a href="http://yoshimi.github.io/downloads.html" target="_blank" rel="noopener noreferrer">http://yoshimi.github.io/downloads</a> & get the latest <code>tar.gz</code> from <a href="https://github.com/Yoshimi/yoshimi/tags" target="_blank" rel="noopener noreferrer">github</a> # Synth </br></br>
 &nbsp;&nbsp;&nbsp;&nbsp; ***NOTE** You may need to move the file to where you can change-directory ("cd" command in the terminal) to the location. It may drop to the "Desktop" or <code>/home/kubuntu/Downloads</code>. If it's the Downloads try <code>sudo ./Downloads</code> & if that works you'll see "~/Downloads$" in the terminal. Next open the file with this: <code>sudo tar -xvzf yoshimi-2.3.2.tar.gz</code>*


</br></br>

### Telegram & Signal Messenging
&nbsp;&nbsp;&nbsp; I'm grabbing Telegram upfront (I use this as a cloud storage pass between my phone & PC).

<code>sudo snap install telegram-desktop</code>

</br></br>

&nbsp;&nbsp;&nbsp; I'm grabbing Signal Desktop Next (I use this as a notepad between my phone & PC).
  
 1) <code>curl -fsSL https://updates.signal.org/desktop/apt/keys.asc | sudo gpg --dearmor -o /etc/apt/keyrings/signal-desktop-keyring.gpg</code>
  
 2) <code>echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/signal-desktop-keyring.gpg] https://updates.signal.org/desktop/apt xenial main" | sudo tee /etc/apt/sources.list.d/signal.list</code>
  
 3) <code>sudo apt update && sudo apt install signal-desktop</code>

</br></br>

### Vtuber Apps
&nbsp;&nbsp;&nbsp; Vtubing may not have a tone of options on Linux but VSeeFace & SysMocap have been known to work through Lutris or Wine (both installed earlier), with Lutris working best for Linux 24+ versions. Next we are going to go through the process of getting SysMocap to work on Linux but before that I will give some quick tips to getting any windows based app/game to work via Lutris/Wine (both use same underlying tech and game runners).

</br></br>

#### Lutris/Wine Tips
 1) Use an installer to initate the file save, then configure the runners and settings before launching after installed via MSI or stand-alone installer
 2) Sometimes you need to use a game runner to be able to use menus then get everything ready, exit change runners then load again to then play/use the game/app
 3) Having the correct font makes a world of difference
 4) Find out what dependencies are needed, sometimes you need to lock a dependency to an app especially if the app/game uses an older dependency
 5) Lutris Runtime can mimic old computer systems some games may rely on for timing or starting/DRM processes

</br>

##### Specifically SysMocap Lutirs/Wine Tips <sup>*[**FOLLOW IN THIS ORDER**]*</sup>
 1) Fully update your npm and nodejs by reinstalling them (do not clean these if there are vulnable dependencies because some of the SysMocap dependencies are now days vulnable)
 2) Use winetricks to turn on and activate: all codex, .net data, C++ data, (your GPU specific extras), directdraw and dirc, 3D rendering services
 3) Usd Lutris to add an exe -> use windows MSI installer file for the exe -> proceed to install process to setup the folders and enviroment for Lutris -> successfully exit without Launch
 4) Configure File to run with machine libraries, do not disable lutris runtime, use Ubuntu 9 rebuild runners, Use no-fsync/e-sync nor DRMs, setup your needed GPU/intergrated-graphics toggles now
 5) Run (it may not pull up first time, if so close with lutris then open again this time debugger should run and app should appear visible after that) -> Setup your settings and character but your cameras shouldn't work correctly -> safely exit
 6) Configure file to run on compatable windows x86 or the correct bit formation for sysmocap then run as is with rest of specs
 7) Run (should run on first try and debugger may run) -> use Mocap feature and enjoy

</br></br>

#### SysMocap
&nbsp;&nbsp;&nbsp; You can visit <a href="https://github.com/xianfei/SysMocap" target="_blank" rel="noopener noreferrer">https://github.com/xianfei/SysMocap</a> to obtain the linux source files and/or the Windows MSI (installer). Following will be the code to get the base application installed.

<code>git clone https://github.com/xianfei/SysMocap.git</code> # Do Not Use "sudo"

<code>sudo apt-get install nodejs</code> # Js Libraries

<code>cd SysMocap</code> # sets to the app folder

<code>npm install</code> # Do Not Use "sudo" | Installs NPM (used as a Linux Installer) </br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ***NOTE:**  DO NOT CLEAN NPM && DO NOT AUDIT FIX NPM NOR AUDIT NPM*

<code>npm start</code> # Do Not Use "sudo" | Runs SysMocap </br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ***NOTE:**  YOU MAY NEED TO SET FLAGS TO HANDLE YOUR SPECIFIC GPU/iGPU SCENERIO TO GET BETTER PERFORMANCE AND/OR TO RUN THE APPLICATION*

***NOTE:** YOU MAY HAVE TO SET PERMISSIONS EVEN THOUGH INSTALLED WITH NO EXTRA PERMISSIONS*

</br></br>

&nbsp;&nbsp;&nbsp; If you have issues after install getting the app to run like a white screen error, here are some helpful tips to get you past this error (normally a vue error for specifically the white screen error upon loading):

  A) Lock various dependencies to their needed version for this application. ***For example:** Vue3 is a more common version of vue to have on Kubuntu with Nvidia GPUs so locking the version for SysMocap to vue2 will prevent global variable changes from preventing vue creating the display (white screen error).*
  B) You may need to nuke your install package.json and reinstall with your needed GPU repository and dependecies to bypass some white screen errors.


</br></br>

### Close the Konsole
***1)** &nbsp;&nbsp; Close the terminal program Konsole (click the "x" in top right of window box).*

***2)** &nbsp;&nbsp; Now reopen it again to begin with the last few installing steps.*
 

</br></br>

### Get new Eyes  <sup>*(Foss Android Webcam)*</sup>
&nbsp;&nbsp;&nbsp; I use DroidCam X for my main webcam system. FOSS & usefull.

  
Visit: <a href="https://www.dev47apps.com/droidcam/linux/" target="_blank" rel="noopener noreferrer">www.dev47apps.com/droidcam/linux</a> & click "Install" to get the following commands.

<code>cd /tmp/
wget -O droidcam_latest.zip https://files.dev47apps.net/linux/droidcam_2.1.3.zip</code>
  </br>&nbsp;&nbsp; **there's a return between /tmp/ & wget so that's basically two commands-in-one**

<code>unzip droidcam_latest.zip -d droidcam</code>

<code>cd droidcam && sudo ./install-client</code>

<code>sudo apt install libappindicator3-1</code>

<code>sudo apt install linux-headers-&#96;uname -r&#96; gcc make</code>

<code>sudo ./install-video</code>
</br>&nbsp;&nbsp; **you will need to know where your os keys are located**

<code>sudo ./install-sound</code>

<code>sudo apt-get install adb</code>


</br></br>

### Flatpak for More
&nbsp;&nbsp;&nbsp; Flatpaks are how many of the older ubuntu and pre-21 upgrade applications are being saved for future use. Many applications broke after the 21 upgrade with ubuntu and most linux distros. Flatpaking is one way to revive the old applications of linux wihtout majorly patching the program. This is why Flatpak's have growing in popularity the past few years.

 </br></br>
 
&nbsp;&nbsp;&nbsp;&nbsp; Visit: <a href="https://flathub.org/setup/Kubuntu" target="_blank" rel="noopener noreferrer">flathub.org/setup/Kubuntu</a> to get the following commands.

<code>sudo apt install flatpak</code>

</br>&nbsp;&nbsp; **Try this first script**
<code>sudo apt install plasma-discover-backend-flatpak</code>

<code>sudo apt install plasma-discover-flatpak-backend</code> </br>&nbsp;&nbsp; **this second script should ONLY BE USED IF THE SCRIPT BEFORE THIS FAILED**

</br>&nbsp;&nbsp; **This Next Script is the last step**
<code>flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo</code>

</hr>
</br></br>

### Off & Back-On
&nbsp;&nbsp;&nbsp; Turn off and then back-on the system and go back into linux. At this point, this should directly load back into linux if the shutdown process goes correctly (fully shuts down without needing to click enter). </br></br>**If shutdown messes up, you'll have to hit enter then if it doesn't shutdown in 40 seconds or less, you'll have to hold the button and hard-shut-down the machine.**


</br></br>

### Discover the App-Store
&nbsp;&nbsp;&nbsp; Now that you have flatpak & snaps, there should be more options in the Discover store. Go find your fun apps, games, and known flatpaks before continuing to the finial upgrade.


</br></br>

### Edit & Upgrade
&nbsp;&nbsp;&nbsp; Edit the theme & do the little things in the settings (main linux settings & browser settings). Once you are done getting your desktop feeling and looking good, insert this into the terminal:
</br></br>
<code>sudo apt-get update</code>
</br></br>
<code>sudo apt-get upgrade</code> </br></br>&nbsp;&nbsp; **This may take quite some time and there's a chance it'll fail the first time. If it does fail, it'll have you retype the command <code>sudo apt-get</code> then the special bit stated on screen (<i>copy and paste with mouse</i>) then click the "Enter" key wait for finish then reinsert <code>sudo apt-get upgrade</code> & hit the "Enter" key again.**


 </br><hr></br></br>

 


 
 
 
 
 
 
 







