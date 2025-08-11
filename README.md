# CS2-LAN-2025

Hier mit Linux (Ubuntu).
Original Doku von Valve: https://developer.valvesoftware.com/wiki/Counter-Strike_2/Dedicated_Servers

## Steamcmd für Ubuntu installieren: 

```bash
sudo apt update && sudo apt install curl
sudo add-apt-repository multiverse; sudo dpkg --add-architecture i386; sudo apt update
sudo apt install steamcmd
``` 

## Steam User nutzen (empfohlen)
```bash
sudo useradd -m steam
sudo passwd steam

sudo -u steam -s
cd /home/steam
```
## CS2 installieren

```bash
steamcmd
```

eventuell ist der Pfad nicht korrekt gesetzt, dehalb bei mir
```bash
/usr/games/steamcmd
```

dann sollte sich eine Steam CLI öffnen.

```steam>
force_install_dir /home/steam/cs2
login anonymous
app_update 730 validate
quit
```

startscript zb start_cs2_lan in **/home/steam** ablegen und ausführbar machen
```bash
chmod +x /home/steam/start_cs2.sh
```
```bash
./start_cs2.sh
```

In meinem Fall kann cs2 den **steamclient.so** nicht finden, weil ein Falsche Pfad hinterlegt ist, Symlink kann das fixen.

```bash
ln -s /home/steam/.steam/steam/steamcmd/linux64 /home/steam/.steam/sdk64
```

Um die Practice und Competetive Configs zu nutzen sollten die .cfg Dateien in
**/home/steam/cs2server/game/game/csgo/cfg/** abgelegt werden.

Practice starten:           ```exec prac```
Competeive Modus starten:   ```exec comp```
Competetive Match starten:  ```exec gogogo```




