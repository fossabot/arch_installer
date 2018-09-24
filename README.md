
<html>
<p align="center">
    <img src="https://cdn.iconscout.com/icon/free/png-256/linux-13-532188.png">
</p>
<h2 align="center">Archlinux Installer</h2>
    <p align="center">
   An installer aimed for developers, peoples that want out of the box things
    <br>
    By archlinux user, for archlinux users
</p>
    
 # Table of Contents

- [Introduction](#introduction)
- [Screenshots](#screenshots)
- [Detail](#detail)
- [Usage](#usage)
- [MyChanges](#mychanges)
- [Credits](#credits)
- [License](#license)

# Introduction 

After installing arch for the first time by manually typing every commands
carefully. I realized that those commands will be forgotten soon enough and I
have to do the hard work again when reinstalling arch. Unfortunately I did not
know shell script very well at that time to automate stuff like that

That's why I wrote this script now. This is the wizard that help installing
arch less painful because I do not reinstall my system regularly, I use arch
for that reason as I don't want to install or update my OS again, just use it
and move on with my life, but if I have to someday then it should not be much
of a chore as right now

This script is heavily inspired from [aui][1], many functions and logic is copied
from there, you should use that one instead as this one is customized to my
machine and setup and not guarantee to work on your computer. [aui][1] is more
customizable, well maintained and have more options than my script anyway

# Screenshot 

Here, the sddm theme that you will get : 

<img src=https://raw.githubusercontent.com/DraGiuS/arch_installer/master/sddm.png width="950"/>

Currently, the desktop look like this : 

Changed the default plasma menu with : https://github.com/divinae/umenu

<img src=https://raw.githubusercontent.com/DraGiuS/arch_installer/master/menu.png width="950"/>

Quarter tiling in action : 

<img src=https://raw.githubusercontent.com/DraGiuS/arch_installer/master/quarter-tiling.png width="950"/>

# Detail

* This script will only run on UEFI systems
* At the beginning you have to choose 4 partitions for: root, home, boot and swap
* After that it will format boot partition as fat32, /home in xfs (better for data), and the rest in ext4
* I currently use KDE so the code installing i3 and xfce4 is not tested yet

#  Usage

* Download arch ISO file from [here][2]
* Use [rufus][3] (most stable to me) to make a bootable USB using the arch image
* Reboot to the usb
* Get the script and run it

**Note:** You should install in the correct order from 1-n because I did not
check all cases

```bash
wifi-menu # if you use wifi

pacman -Sy git

git clone https://github.com/DraGiuS/arch_installer

cd arch_installer

it's recommended to edit the "common" file

chmod u+x install

./install

```

* After installing the base system choose finish to reboot. A copy of this repo
is placed in the root directory. Go to there and run the other script

```bash
git clone -b postinstall https://github.com/DraGiuS/arch_installer

cd arch_installer

chmod u+x postinstall

./postinstall
```

# MyChanges
* Kde unstable option

* Added some packages, aur or not..

* Changed grub, plasma, sddm, icons themes

* Default setup of zsh with powerlevel9k

* Quarter tiling for Plasma

* Octopi

* Keyboard layout support

* Support of translation for main apps

* More wallpapers by default 

* Conky

* Colorscheme for konsole

#  Credits

* [aui][1]
* https://github.com/bhilburn/powerlevel9k
* https://github.com/divinae/umenu
* https://github.com/divinae/uswitch
* https://github.com/RadRussianRus/sddm-slice
* https://github.com/fahrud26/Conky-Themes 
* https://github.com/arcticicestudio/nord-konsole
* https://github.com/ishovkun/SierraBreeze
* https://github.com/Dacha204/grub2-themes-Ettery
* https://code.chakralinux.org/tools/heritage
* https://github.com/Jazqa/kwin-quarter-tiling
* https://github.com/NearHuscarl/arch_installer
* https://github.com/robbyrussell/oh-my-zsh
* Archlinux team
* ME ('cause i love me)
# License

[**BSD 3-Clauses**](../master/LICENSE.md)

[1]: https://github.com/helmuthdu/aui
[2]: https://www.archlinux.org/download/
[3]: https://rufus.akeo.ie/
