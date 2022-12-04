---
layout: default
---

[back](./)

# Installation guidelines and tips
    
## Installation logiciels
### Linux Ubuntu 22.04 LTS « Jammy Jellyfish »
>> Disponible depuis avril 2022, elle sera maintenue jusqu'en avril 2027.  
[Création d’une clé USB d’installation](https://www.windows8facile.fr/creer-cle-usb-ubuntu-22-lts-desktop/)  
Langue choisie : English  

### Visual Studio Code
- the repository and key can be installed manually with the following script:
```shell
sudo apt-get install wget gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg
sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
rm -f packages.microsoft.gpg
```
- Then update the package cache and install the package using:
```shell
sudo apt install apt-transport-https
sudo apt update
sudo apt install code # or code-insiders
```
- If you see an error when deleting files from the VS Code Explorer on the Debian operating system, it might be because the trash implementation that VS Code is using is not there. Run these commands to solve this issue:
```shell
sudo apt-get install gvfs-bin
```

### Git
```shell
# apt-get install git
```

### Anaconda
- Make sure your System is up to date : 
```shell
sudo apt-get update -y && sudo apt-get upgrade -y
```
- Télécharger la [distribution anaconda pour linux]([./another-page.html](https://www.anaconda.com/products/distribution#linux)).
- Compare the checksum with [this one](https://docs.anaconda.com/anaconda/install/hashes/) :
```shell
md5sum /home/renaud/Downloads/Anaconda3-2022.10-Linux-x86_64.sh
```
- Install : 
```shell
sudo bash /home/renaud/Downloads/Anaconda3-2022.10-Linux-x86_64.sh
```
- Accept the Agreement and confirm the location.
- "Do you wish the installer to initialize Anaconda3 by running conda init?" --> `yes`

- To activate our installation :
```shell
source ~/.bashrc
```

- To update anaconda-navigator :
```shell
conda deactivate
conda update anaconda-navigator
```

- If you'd prefer that conda's base environment not be activated on startup, set the auto_activate_base parameter to false: 
```shell
conda config --set auto_activate_base false
```


[conda-cheatsheet.pdf](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf)

accès à anaconda navigator terminal



[back](./).

