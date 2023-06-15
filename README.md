# Install Matlab on Linux 
Install the binary of matlab on any Linux Distro, including an Appstarter to launch it

Installing Matlab on Linux is annoying. But if done right, its not actually hard, here are the needed commands:

![Mathworks Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/2/21/Matlab_Logo.png/200px-Matlab_Logo.png)

## 1. Download Matlab

save `Matlab_R<VERSIONNUMBER>.zip` to a folder like `/home/USERNAME/Programs`

```
cd ~/Programs &&\
mkdir INSTALL &&\
unzip -X -K matlab_* &&\
rm -f matlab_*.zip
./install

# activation should now be done in the installer
# choose "INSTALL" in the same directory as the download dir
# this works on immutable distros and also helps with the integration
```

## GUI integration

```
wget https://github.com/trytomakeyouprivate/Matlab-Linux-Install/raw/main/MATLAB-GUI-INSTALL
chmod +x MATLAB-GUI-INSTALL
./MATLAB-GUI-INSTALL
```

- bashrc, zshrc, fish integration
- Icon in the appmenu
- mimetype, so .m files should be automatically opened


Install the Matlab Packamanager MPM to get updates:

```
wget https://www.mathworks.com/mpm/glnxa64/mpm -P ~/.bin/
chmod +x ~/.bin/mpm
```

Usage:

```
mpm install --release=<release> --destination=<destination> [--products] <product1> <product2>
# for example:

mpm install --release=R2022a --destination=/home/user/Programs/matlab --products MATLAB
```

## Current problems
All problems solved for now.

Version numbers seem to no longer be a problem
