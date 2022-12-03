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
[conda-cheatsheet.pdf](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf)

accès à anaconda navigator terminal



[back](./).

