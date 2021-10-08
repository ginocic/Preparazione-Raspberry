Installazione del sistema operativo e del software necessario e preparazione al primo utilizzo del Raspberry

# Installare e configurare Raspberry Pi OS
Scaricare e installare [Raspberry Pi Imager](https://www.raspberrypi.com/software/).

![Download Raspberry Pi Imager](img\download rpi-imager.PNG)









il software necessario su Raspberry Pi

### Preparazione
```bash
cd
passwd
sudo apt install -y git curl
mkdir -p "$HOME/.local"
git clone https://github.com/ginocic/bash_aliases.git "$HOME/.local/BashAliases"
```

Test
```bash
. "$HOME/.local/BashAliases/bash_aliases"
```

Scrittura nel file ```.bashrc```
```bash
echo '. "$HOME/.local/BashAliases/bash_aliases"' >> ~/.bashrc
tail -5 ~/.bashrc
```

Testare in una sessione ssh duplicata e se tutto funziona correttamente
```bash
aggiorna && ripulisci
riavvia
```

### Note
Se si vuole disabilitare bluetooth e WiFi, aprire il il file `config.txt` con `nano`
```bash
sudo nano /boot/config.txt
```
Trovare la seguente linea
```
# Additional overlays and parameters are documented /boot/overlays/README
```
e aggiungere queste 2 linee sotto
```
dtoverlay=disable-wifi
dtoverlay=disable-bt
```
