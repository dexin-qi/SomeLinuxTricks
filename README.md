# SomeLinuxTricks
Some Linux Trick to help you fix problems

## How to use order `tree`
Use `tree -L 2 -d` to list Level 2 directories.

Use `tree --help` to list this command's help files.

## How to install Shadowsocks :smirk:
```bash
sudo add-apt-repository ppa:hzwhuang/ss-qt5
sudo apt-get update
sudo apt-get install shadowsocks-qt5
```
## How to set SwitchyProxyOmega AutoProxy
```
https://raw.githubusercontent.com/gfwlist/gfwlist/master/gfwlist.txt
```

## How to set Flatabulous theme :heart:
```bash
sudo add-apt-repository ppa:noobslab/themes
sudo add-apt-repository ppa:noobslab/icons  
sudo apt update 
sudo apt install unity-tweak-tool
sudo apt install flatabulous-theme
sudo apt install ultra-flat-icons
```

## How to setup grub files to enable the NVIDIA GPU for ThinkPad S5 Gen2 :+1:
Add `rcutree.rcu_idle_gp_delay=2 acpi_osi=Linux` options to `/etc/default/grub` Line `GRUB_CMDLINE_LINUX_DEFAULT`
**Final Views** of Line `GRUB_CMDLINE_LINUX_DEFAULT` should be:
`GRUB_CMDLINE_LINUX_DEFAULT="quiet splash rcutree.rcu_idle_gp_delay=2 acpi_osi=Linux"`

## Where to find GitHub's Markdown Format
[Overview](https://guides.github.com/features/mastering-markdown/#GitHub-flavored-markdown)

[Emoji Sheet](https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md)

## How to install ROS kinetic
```bash
sudo sh -c '. /etc/lsb-release && echo "deb http://mirrors.ustc.edu.cn/ros/ubuntu/ $DISTRIB_CODENAME main" > /etc/apt/sources.list.d/ros-latest.list'
```
```bash
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654 && sudo apt-get update
```
```bash
sudo rosdep init && rosdep update
```
```bash
echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc && source ~/.bashrc
```
```bash
sudo apt-get install python-rosinstall
```

## How to relize ttyUSB port readable
```bash
sudo usermod -aG dialout ${USER}
```