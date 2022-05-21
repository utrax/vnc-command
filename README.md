# vnc-command
The VNC-command repository contain a set of command that is used for configuring a VNC connection to any Linux computer just only by using terminal 
================
Commands:
================
sudo apt update
sudo apt install lightdm
sudo reboot
sudo apt install x11vnc

sudo nano /lib/systemd/system/x11vnc.service

!Copy and paste these commands - change the password
[Unit]
Description=x11vnc service
After=display-manager.service network.target syslog.target

[Service]
Type=simple
ExecStart=/usr/bin/x11vnc -forever -display :0 -auth guess -passwd password
ExecStop=/usr/bin/killall x11vnc
Restart=on-failure

[Install]
WantedBy=multi-user.target

!Save file and run these commands:

systemctl daemon-reload
systemctl enable x11vnc.service
systemctl start x11vnc.service
systemctl status x11vnc.service

================
