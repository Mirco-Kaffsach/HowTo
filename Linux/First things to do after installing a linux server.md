
> [!NOTE] Caution
> These are my personal first steps after installing a Linux server based on Debian. The current version is Debian 12, but this may change over time.
> 
> I always try to keep the steps up to date and adapt them to the respective operating system version and, if necessary, add steps that are no longer required or additionally required.
> 
> Under no circumstances will I accept any liability for the correctness and completeness of these steps!
> 
> If these code snippets are used, this is always at your own risk!
> 
> I use '*nano*' whenever I need a text editor. You can of course use the text editor of your choice, but make sure you adapt the commands to your text editor.

- Switch to root
```
su
```
- Refresh update sources and upgrade if updates are available
```
apt update && apt upgrade
```
- Install nala
```
apt install nala
```
- Install sudo
```
nala install sudo
```
- Create a '*scripts*' folder at root and a file '*getupdates.sh*'
```
mkdir /scripts
nano /scripts/getupdates.sh
```
- Paste the following lines into the script file
```
clear
sudo nala update && sudo nala upgrade && sudo nala autoremove && sudo nala autopurge && sudo nala clean
```
- Configure unattended upgrades
```
sudo nala install unattended-upgrades apt-listchanges -y && sudo dpkg-reconfigure -plow unattended-upgrades
```
