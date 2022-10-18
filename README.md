# Matlab-Linux-Install-script
Install the binary install of matlab in any Linux Distro (Appstarter for KDE)

Installing Matlab on Linux is annoying. But if done right, its not actually hard, here are the needed commands:

## 1. Download Matlab

save `Matlab_R<VERSIONNUMBER>.zip` to a folder like `/home/USERNAME/Programs`

```
cd ~/Programs
unzip -X -K matlab_*
sudo ./install

# activate
sh /usr/local/MATLAB/R2022b/bin/activate_matlab.sh
```
`
## create Appstarter for KDE

If Appstarters in GNOME and Cinnamon work differently, please create a pull request.

```
sudo printf "[Desktop Entry]\n Version=1.0\nType=Application\nExec=/usr/local/MATLAB/R2022b/bin/matlab %F\nName=MATLAB\nIcon=/usr/local/MATLAB/R2022b/bin/glnxa64/cef_resources/matlab_icon.png\nCategories=Development;Math;Science\nComment=Scientific computing environment\nStartupNotify=true\nStartupWMClass=com-mathworks-util-PostVMInit" > /usr/share/applications/matlab.desktop

chmod +x /usr/share/applications/matlab.desktop
```

Thats it! Matlab is now installed and available like a normal Application. For updates what you should do is install the Matlab Packamanager MPM:

```
wget https://www.mathworks.com/mpm/glnxa64/mpm
chmod +x mpm
```
`
Usage:

```
mpm install --release=<release> --destination=<destination> [--products] <product1> <product2>
# for example:

mpm install --release=R2022a --destination=/home/user/Programs/matlab --products MATLAB
```
