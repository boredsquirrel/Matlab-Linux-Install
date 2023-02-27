# Install Matlab on Linux 
Install the binary of matlab on any Linux Distro, including an Appstarter to launch it

Installing Matlab on Linux is annoying. But if done right, its not actually hard, here are the needed commands:

![Mathworks Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/2/21/Matlab_Logo.png/200px-Matlab_Logo.png)

## 1. Download Matlab

save `Matlab_R<VERSIONNUMBER>.zip` to a folder like `/home/USERNAME/Programs`

```
cd ~/Programs
unzip -X -K matlab_*
#rm -f matlab_*.zip
sudo ./install

# activate
sh /usr/local/MATLAB/R2022b/bin/activate_matlab.sh #replace version with current number
```

## create Appstarter

```
sudo printf """[Desktop Entry]
Type=Application
Exec=/usr/local/MATLAB/R2022b/bin/matlab %F
Name=Matlab
Icon=/usr/local/MATLAB/R2022b/bin/glnxa64/cef_resources/matlab_icon.png
Categories=Development;Math;Science
Comment=Scientific computing environment
StartupNotify=true
StartupWMClass=com-mathworks-util-PostVMInit""" > ~/.local/share/applications/matlab.desktop

chmod +x ~/.local/share/applications/matlab.desktop
```

Thats it! Matlab is now installed and available through the App menu. Install the Matlab Packamanager MPM to get updates:

```
wget https://www.mathworks.com/mpm/glnxa64/mpm -P ~/.local/bin/
chmod +x ~/.local/bin/mpm
```

Usage:

```
mpm install --release=<release> --destination=<destination> [--products] <product1> <product2>
# for example:

mpm install --release=R2022a --destination=/home/user/Programs/matlab --products MATLAB
```

## Current problems
You need to manually edit the version numbers for
- activating
- icon in Appstarter
- program in Appstarter

also the appstarter has to be renewed when the program updates, depending on the folder probably

This has to be automated using for example the version number of the Matlab download. I dont have time for this and dont use Matlab currently, feel free to create a pull request
