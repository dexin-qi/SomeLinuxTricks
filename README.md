# SomeLinuxTricks
Some Linux Trick to help you fix problems

## How to use order `tree`
Use `tree -L 2 -d` to list Level 2 directories.

Use `tree --help` to list this command's help files.

## How to setup grub files to enable the NVIDIA GPU for ThinkPad S5 Gen2 :+1:
Add `rcutree.rcu_idle_gp_delay=2 acpi_osi=Linux` options to `/etc/default/grub` Line `GRUB_CMDLINE_LINUX_DEFAULT`
**Final Views** of Line `GRUB_CMDLINE_LINUX_DEFAULT` should be:
`GRUB_CMDLINE_LINUX_DEFAULT="quiet splash rcutree.rcu_idle_gp_delay=2 acpi_osi=Linux"`
```bash
sudo update-grub
```

## Blacklist noveau driver
```bash
sudo gedit /etc/modprobe.d/blacklist.conf 
```
```
blacklist vga16fb
blacklist nouveau
blacklist rivafb
blacklist rivatv
blacklist nvidiafb 
```
```bash
sudo update-initramfs -u 
```
Reboot Ubuntu system
```bash
lsmod | grep nouveau
```

## How to install CUDA (with NVIDIA driver)
Just install CUDA is enough! It will automaticly install NVIDIA driver.
```bash
sudo dpkg -i cuda-repo-ubuntu1604-9-0-local_9.0.176-1_amd64.deb
sudo apt-key add /var/cuda-repo-9-0-local/7fa2af80.pub
sudo apt-get update
sudo apt-get install cuda
```
Add environment PATH value to ~/.bashrc
```
export PATH=/usr/local/cuda-9.0/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64:/usr/local/cuda-9.0/extras/CUPTI/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
```

## How to install cudnn
Unzip the cudnn package
```bash
sudo cp cuda/include/cudnn.h /usr/local/cuda/include
sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*
```

## How to install Shadowsocks :smirk:
```bash
sudo add-apt-repository ppa:hzwhuang/ss-qt5
sudo apt-get update
sudo apt-get install shadowsocks-qt5
```

## How to install indicator-sysmonitor
```bash
sudo add-apt-repository ppa:fossfreedom/indicator-sysmonitor  
sudo apt-get update  
sudo apt-get install indicator-sysmonitor 
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