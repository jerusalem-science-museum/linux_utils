# Ubuntu

## Install AnyDesk
```curl -o /tmp/anydesk.deb https://download.anydesk.com/linux/anydesk_5.1.2-1_amd64.deb && sudo dpkg -i /tmp/anydesk.deb```

## Install Common Packages
```sudo apt install -y gnome-tweak-tool openssh-server samba```

## Install Development Packages
```
sudo snap install --classic code
sudo snap install --classic sublime-text
sudo snap install --classic --beta github-desktop
```

## Enable Samba
```
sudo sh -c "cat > /etc/samba/smb.conf <<EOF
[user]
    comment = Samba on Ubuntu
    path = /home/user
    read only = no
    browsable = yes
EOF"
sudo service smbd restart
sudo ufw allow samba
sudo smbpasswd -a $USER
```
