# installVoodooHDA4BSnMont
How To install voodooHDA v2.9.7 on Big Sur 11.3 above and Monterey
A workaround to get it to work so that you can enjoy your music :)

Disable csr
Boot to Recovery
In Terminal,

% csrutil disable
% csrutil authenticated-root disable

Set csr-active-config to 0x0285 String in config.plist
()

Mount Big Sur volume with terminal (not sure if this step is required)
% sudo diskutil mountdisk disk1s5

Disable gatekeeper with Hackintool 3.6.1 Utilities since Monterey need the latter version 
()

Download and run VoodooHDA OC.dmg
Drag-n-drop Big Sur volume to install voodooHDA and the preference pane

Copy voodooHDA.kext v2.9.7 to /Volumes/ESP/EFI/OC/Kexts and /L/E with terminal
% sudo cp -R /[path-to-]/VoodooHDA.kext /Volumes/ESP/EFI/OC/Kexts
% sudo cp -R /[path-to]/VoodooHDA.kext /Library/Extensions

Wait for the prompt "System Extension Updated". I think the installation will not work without this prompt

Open System Preferences
()

Click the lock to make changes and Click Allow
()

DO NOT click Restart. Click Not Now
()

Install voodooHDA.kext with Hackintool via kmutil
()

Restart your hackintosh

Enjoy your music :)

--------
How to load voodooHDA if it is not working
sudo kmutil load -p /Library/Extensions/voodooHDA.kext
sudo touch /Library/Extensions

Restart your hackintosh