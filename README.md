<img src="https://raw.githubusercontent.com/vineetred/nGram/vineetred-patch-1/isolated-monochrome-black.svg" width="20%"> </img>

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0) ![crates.io](https://img.shields.io/crates/v/flowy.svg) ![CI](https://github.com/vineetred/flowy/workflows/CI/badge.svg?branch=master)


## Demo
<p align="center">
  <img src="https://github.com/vineetred/flowy/blob/master/demo2.gif?raw=true" alt="Flowy demo"/>
</p>

<p align="center">
  <img src="https://github.com/vineetred/flowy/blob/master/demo.gif?raw=true" alt="Flowy demo"/>
</p>

## Usage
* The documentation can be found at https://docs.rs/flowy.
* You can either download the binary or get the Debian package.
* Flowy comes with a preset ```lake``` set of wallpapers. See the binary section for more information.

### Binary - Recommended
* It can be either found in the Releases section or can be installed using Cargo by running the command ```cargo install flowy```.
* If you use the binary, just run it by typing ```flowy -d``` or ```flowy --dir``` to set the path to the wallpaper directory.
* In case you want to use the preset wallpapers, run ```flowy --preset lake``` or ```flowy -p lake```. This downloads the Lakeside wallpapers made by Louis Coyle. They can also be found [here](https://bucket-more.s3.ap-south-1.amazonaws.com/uploads/lake.tar.gz).
* If you're using Linux, you can either let the binary run forever in a terminal session or setup a ```systemd``` service so it listens in the background. The Debian package does this automatically for you.

### Debian package
* If you use the Debian package, then it will install flowy as a ```systemd``` service. During installation, flowy will ask you your directory. 
* Once the installation is done, run the command ```systemctl --user start flowy.service``` to run the application.
* Once installation is done and you would still like to change the directory, go to the systemd service file found at ```/etc/systemd/user``` and change the directory in that file.

## Wallpapers directory
* The wallpapers inside the directory must be named sequentially.
* For example, if you have 11 wallpapers, the names must be ```paper-01.jpg, paper-02.jpg...```.
* It does not matter what the names of the files are as long as they are sequential.

## Experimental
* By default, flowy evenly sets the wallpaper change time based on the number of wallpapers there are. In case you would like to modify these times, it can be done so by editing the ```times.toml``` file found in the ```/home``` directory. You need to comment the ```flowy::generate_config``` function call in ```main.rs``` and then build it after modifying the config file.

## Supported Environments
* MacOS
* **GNOME Based** - Ubuntu, Fedora, Pantheon
* Linux Mint Cinnamon
* Linux Mint MATE
* Deepin
* XFCE
* KDE

**TODO**
* GUI
* Match the stars given the location
* Add support for other platforms, both UNIX and Windows.
* Refactor OS related code to another file
