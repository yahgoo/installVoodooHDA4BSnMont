# installVoodooHDA4BSnMont
How To install voodooHDA v2.9.7 on Big Sur 11.3 above and Monterey
A workaround to get it to work so that you can enjoy your music :)

Disable csr
Boot to Recovery
In Terminal,

% csrutil disable  
% csrutil authenticated-root disable

Set csr-active-config to 0x0285 String in config.plist
![Screenshot](https://github.com/yahgoo/installVoodooHDA4BSnMont/blob/main/img/Screenshot%202021-07-02%20at%2011.19.57%20AM.png)

Mount Big Sur volume with terminal (not sure if this step is required)
% sudo diskutil mountdisk disk1s5

Disable gatekeeper with Hackintool 3.6.1 Utilities since Monterey need the latter version 
![Screenshot](https://github.com/yahgoo/installVoodooHDA4BSnMont/blob/main/img/Screenshot%202021-07-02%20at%2011.39.53%20AM.png)

Download and run VoodooHDA OC.dmg
Drag-n-drop Big Sur volume to install voodooHDA and the preference pane

Copy voodooHDA.kext v2.9.7 to /Volumes/ESP/EFI/OC/Kexts and /L/E with terminal
% sudo cp -R /[path-to-]/VoodooHDA.kext /Volumes/ESP/EFI/OC/Kexts
% sudo cp -R /[path-to]/VoodooHDA.kext /Library/Extensions

Wait for the prompt "System Extension Updated". I think the installation will not work without this prompt

Open System Preferences
![Screenshot](https://github.com/yahgoo/installVoodooHDA4BSnMont/blob/main/img/Screenshot%202021-07-02%20at%2011.52.39%20AM.png)

Click the lock to make changes and Click Allow
![Screenshot](https://github.com/yahgoo/installVoodooHDA4BSnMont/blob/main/img/Screenshot%202021-07-02%20at%2011.54.00%20AM.png)

DO NOT click Restart. Click Not Now
![Screenshot](https://github.com/yahgoo/installVoodooHDA4BSnMont/blob/main/img/Screenshot%202021-07-02%20at%2011.54.29%20AM.png)

Install voodooHDA.kext with Hackintool via kmutil
![Screenshot](https://github.com/yahgoo/installVoodooHDA4BSnMont/blob/main/img/Screenshot%202021-07-02%20at%2011.57.55%20AM.png)

Set csr-active-config to EF0F0000 DATA String in config.plist
![Screenshot](https://github.com/yahgoo/installVoodooHDA4BSnMont/blob/main/img/Screenshot%202021-07-02%20at%201.47.08%20PM.png)

Restart your hackintosh


--------
How to load voodooHDA if it is not working
% sudo kmutil load -p /Library/Extensions/voodooHDA.kext
% sudo touch /Library/Extensions

Restart your hackintosh

Enjoy your music :)