This configuration is built upon Mrinmoy's configuration: https://gitlab.com/mrinmoyin/dotfiles/-/blob/main/waybar/style.css
It is modified by me using claude code.

![Screenshot_20260208_140004_RVNC Viewer](https://github.com/user-attachments/assets/cdea3d8e-df51-47a8-b1f4-9fc202b6bcb6)

```
sudo pacman -S lact ncdu htop pavucontrol nm-connection-editor swaync ttf-jetbrains-mono-nerd ttf-firacode-nerd ttf-hack-nerd
```
Start waybar in terminal click on the tabs and see the logs, if something failed you might need to enable the service (do it for any of the above packages except swaync):
```
sudo systemctl enable <service>
```
for swaync there might be a notification manager running if you would like to use swaync instead of the default notification manager follow the steps:
check which notification manager you have using:
```
ps aux | grep -E "dunst|mako"
```
then stop it using
```killall mako```
or
```killall dunst```
then start swaync
systemctl --user enable --now swaync.service

If you want to add icons in the windows tabs, open the file modules.json
you can see in "window-rewrite" there is:
"class<application-class-name>": "icon"
this will associate an application with an icon, to know what is the application class name, open the application and run ```hyprctl clients```.
