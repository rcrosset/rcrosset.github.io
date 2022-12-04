---
layout: default
---

[back](./)

# Installation guidelines and tips

*Document initié le 02/08/2022*

## Installation logiciels
### Linux Ubuntu 
#### Installation
- 22.04 LTS « Jammy Jellyfish » disponible depuis avril 2022, elle sera maintenue jusqu'en avril 2027.  
- [Création d’une clé USB d’installation](https://www.windows8facile.fr/creer-cle-usb-ubuntu-22-lts-desktop/)  
- Langue choisie : English  
#### Utilisation
- Templates : placer dans `Home/Templates/` les trames de documents les plus utilisées:
    - trames vides :
```shell
touch Text_file.txt CSV_File.csv 
```
    - trames non-vides :
```shell
echo \#\!/bin/bash > script_shell.bash
echo '#!/usr/bin/env python3' > script_python.py
echo -e '#!/bin/bash\neval "$(conda shell.bash hook)" # bash alternative to conda init\nconda activate my_conda_env\ncd my_dir/\njupyter notebook' > jn_shortcut.bash
echo -e '<!doctype html>\n<html lang="fr">\n<head>\n  <meta charset="utf-8">\n  <title>Titre de la page</title>\n  <link rel="stylesheet" href="style.css">\n  <script src="script.js"></script>\n</head>\n<body>\n  ...\n  <!-- Le reste du contenu -->\n  ...\n</body>\n</html>\n' > HTML_file.html
```

- [Nettoyer Ubuntu](https://doc.ubuntu-fr.org/nettoyer_ubuntu): 
```shell
# pour vider la mémoire vive:
free -h && sudo sysctl vm.drop_caches=3 && free -h
```

### [Google Chrome](https://doc.ubuntu-fr.org/google_chrome)
for professionnal use

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
#### Installation
- installation:
```shell
apt-get install git
```
- Git LFS (Large File Storage):
```shell
git lfs install
```
#### Utilisation

### Anaconda
#### Installation
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
if you have selected `no`, you have to initialize after the installation process is done, first run `source [PATH TO CONDA]/bin/activate` and then run `conda init`.

- To activate our installation refreshing the terminal:
```shell
source ~/.bashrc
```

- To update anaconda-navigator :
```shell
conda deactivate
conda update anaconda-navigator
```
- To verify the installation :
```shell
conda info
```

- If you'd prefer that conda's base environment not be activated on startup, set the auto_activate_base parameter to false: 
```shell
conda config --set auto_activate_base false
```

- To add and give priority to *conda-forge channel*:
```shell
conda config --add channels conda-forge
conda config --set channel_priority strict
conda config --show channels
```

- To face DPI-scaling issue, set `enable_high_dpi_scaling = True` in the Anaconda config:
```shell
nano ~/.anaconda/navigator/anaconda-navigator.ini
```

#### Utilisation

- you can use a bash script (the jn_shortcut.bash template modifying my_conda_env and my_dir) in order to save you some time activating your conda environment and opening jupyter notebooks. 
```shell
chmod 755 jn_shortcut.bash
./jn_shortcut.bash
```

- [conda-cheatsheet.pdf](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf)

- accès à anaconda navigator terminal

- [Jupyter shortcuts](https://opensharing.fr/scripting-python-jupyter-shortcuts)

#### Désinstallation

```shell
conda install anaconda-clean
rm -rf ~/anaconda3
nano ~/.bashrc → effacer ou commenter la ligne export PATH=“/home/username/anaconda3/bin:$PATH”
```

### Other little tools
#### jp2a
- used to convert picture/logo to ASCII in order to display in shell:
```shell
sudo apt install jp2a
```

[back](./).

