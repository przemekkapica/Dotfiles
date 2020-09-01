# **Setting up Fedora Workstation 32 on awesomeWM** *Tutorial with commands*


### Begin setup
```sudo su``` (optional) <br>
```sudo dnf update```



### Install awesomeWM and ready-to-go configs & themes
- Install awesomeWM<br>
```sudo dnf install awesome```

- Set up configs and themes<br>
```git clone https://github.com/przemekkapica/My-awesomeWM-config.git```<br>
```mkdir .config/awesome```<br>
```cd My-awesomeWM-config```<br>
```cp -r * ~/.config/awesome/```

### Install software
- Install Flatpak<br>
```sudo dnf install -y Flatpak```

- Install Snap<br>
```sudo dnf install snapd```

- Install Rofi Laucnher<br>
```sudo dnf install rofi```

- Install Atom<br>
```sudo dnf install $(curl -sL "https://api.github.com/repos/atom/atom/releases/latest" | grep "https.*atom.x86_64.rpm" | cut -d '"' -f 4)```

- Install Sublime Text<br>
```sudo rpm -v --import https://download.sublimetext.com/sublimehq-rpm-pub.gpg```<br>
```sudo dnf config-manager --add-repo https://download.sublimetext.com/rpm/stable/x86_64/sublime-text.repo```<br>
```sudo dnf install sublime-text```

- Install Visual Studio Code<br>
```sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc```<br>
"cat <<EOF | sudo tee /etc/yum.repos.d/vscode.repo
[code]
name=Visual Studio Code
baseurl=https://packages.microsoft.com/yumrepos/vscode
enabled=1
gpgcheck=1
gpgkey=https://packages.microsoft.com/keys/microsoft.asc
EOF"<br>
```dnf check-update```<br>
```sudo dnf install code```

- Install Spotify (flatpak)<br>
```sudo flatpak install -y --from https://flathub.org/repo/appstream/com.spotify.Client.flatpakref```

- Install Cinnamon DE<br>
```sudo dnf -y group install "Cinnamon Desktop"```

- Install VirtualBox by Oracle<br>
```sudo wget http://download.virtualbox.org/virtualbox/rpm/fedora/virtualbox.repo -P /etc/yum.repos.d/```<br>
```sudo dnf update```<br>
```sudo dnf install @development-tools```<br>
```sudo dnf install kernel-devel kernel-headers dkms qt5-qtx11extras  elfutils-libelf-devel zlib-devel```<br>
```sudo dnf install VirtualBox-6.1```

- Install i3lock<br>
```dnf install i3lock```

- Install Gpick<br>
```dnf install gpick```

- Install Brave Browser<br>
```sudo dnf config-manager --add-repo https://brave-browser-rpm-release.s3.brave.com/x86_64/```<br>
```sudo rpm --import https://brave-browser-rpm-release.s3.brave.com/brave-core.asc```<br>
```sudo dnf install brave-browser```

- Install Tor Browser<br>
```sudo dnf install torbrowser-launcher```

- Install Compton<br>
```sudo dnf install compton```

- Install Flameshot<br>
```sudo dnf install flameshot```

- Install htop<br>
```sudo dnf install htop```

- Install VLC Media Player<br>
```sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm```<br>
```sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm```<br>
```sudo dnf install vlc```<br>
```sudo dnf install python-vlc``` (optional)

- Install feh<br>
```sudo dnf install feh```

- Install Z Shell<br>
```sudo dnf install zsh```

- Install lxappearance<br>
```sudo dnf install lxappearance```

- Install fail2ban<br>
```sudo dnf install fail2ban```

### Set up other configs & themes
- Clone my github repository<br>
```git clone https://github.com/przemekkapica/Dotfiles-and-Configs.git```

- Set up configs and themes<br>
```cd Dotfiles-and-Configs/```<br>
```cp .bashrc ~/```<br>
```cp .zshrc ~/```<br>
```mkdir ~/.config/rofi``` (if directory does not exist)<br>
```cp rofi/theme.rasi ~/.config/rofi/```

- Set Zsh as a default shell<br>
```sudo chsh --shell /bin/zsh <your_username>```

- Install powerlevel10k zsh theme<br>
```git clone https://github.com/romkatv/powerlevel10k.git```<br>
Restart zsh and type ```p10k configure``` if configuration will not appear automatically.

### End configuration and reboot system
```sudo reboot```


Fedora is finally ready to use ;)
