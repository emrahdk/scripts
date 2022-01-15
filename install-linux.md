# Linux 

## After installing Pop!_OS

> https://jacci.net/linux/pop-os/how-to-install-grub-on-pop-os-20-04/
> https://www.youtube.com/watch?v=hbzCSjlbInY

1. `sudo apt update && sudo apt upgrade` 
2. `sudo apt install grub-efi grub2-common grub-customizer`
3. `sudo grub-install`
4. `sudo cp /boot/grub/x86_64-efi/grub.efi /boot/efi/EFI/pop/grubx64.efi` 
5. Launch grub-customizer
    1. File > Change environment
    2. Change _OUTPUT_FILE_ value to `/boot/efi/EFI/pop/grub.cfg`
    3. Check _save this configuration_
    4. Click _Apply_x
    3. Change order (optional)
    4. Save
6. Reboot

## Configure Pop
1. Install hide top bar
    1. https://github.com/mlutfy/hidetopbar
    2. `sudo apt install gnome-shell-extension-autohidetopbar`
2. Add Burn My Windows 
    1. Install from GNOME extensins    
3. Switch to High Performance profile
    1. Open Startup Applications
    2. Add the following command `system76-power profile performance`
4. Change ALT-Tab to Switch windows
    1.  Settings > Keyboard > Keyboard Shortcuts >Customize Shortcuts
    2.  Search for "Switch windows" and change it

## Configure Git
1. Set up SSH
2. Set reconcilations strategy:
    - `git config pull.rebase true`

## Configure terminal
1. Install ZSH: `sudo apt install zsh`
2. Install Oh My Zsh
3. Use the Oxide theme
4. Install terminator 
5. Add CSS customization

## Install apps
1. Brave
    2. Add to Sync chain
2. Node
3. Code
4. Spotify
5. Signal
6. Teams
