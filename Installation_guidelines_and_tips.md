---
layout: default
---

[back](./)

## Installation guidelines and tips
    
### Installation logiciels
#### Linux Ubuntu 22.04 LTS « Jammy Jellyfish »
Disponible depuis avril 2022, elle sera maintenue jusqu'en avril 2027.  
[Création d’une clé USB d’installation](https://www.windows8facile.fr/creer-cle-usb-ubuntu-22-lts-desktop/)  
Langue choisie : English  

#### Anaconda
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

<p>Click on the button to copy the text from the text field. Try to paste the text (e.g. ctrl+v) afterwards in a different window, to see the effect.</p>

<input type="text" value="Hello World" id="myInput">

<div class="tooltip">
<button onclick="myFunction()" onmouseout="outFunc()">
  <span class="tooltiptext" id="myTooltip">Copy to clipboard</span>
  Copy text
  </button>
</div>

<script>
function myFunction() {
  var copyText = document.getElementById("myInput");
  copyText.select();
  copyText.setSelectionRange(0, 99999);
  navigator.clipboard.writeText(copyText.value);
  
  var tooltip = document.getElementById("myTooltip");
  tooltip.innerHTML = "Copied: " + copyText.value;
}

function outFunc() {
  var tooltip = document.getElementById("myTooltip");
  tooltip.innerHTML = "Copy to clipboard";
}
</script>

[back](./).

