# Squit Proxyserver

## Ausgangslage

In unserem Praktikum haben wir ein Netzwerk aufgebaut. Dieses enthilt zwei Firewalls, ein DNS-, ein Proxy-, ein DHCP-Server, ein RADIUS und drei Zugangspunkte. Unsere Aufgabe war, den Proxyserver einzurichten.

## Intro

Ein Proxy bzw. ein Proxy-Server ist ein Vermittler innerhalb eines Netzwerks. Er wird zwischen Nutzer und Netzwerk-Ressource geschaltet. Nutzer, die ins Internet gehen und einen Proxy nutzen, nehmen also einen Umweg. Durch diesen Umweg kann unter anderem die Kommunikation zwischen Nutzer und Netzwerk-Ressource abgesichert, verschleiert oder beschleunigt werden. Neben den Funktionen von Standard-Proxys gibt es auch Reverse-Proxys, die vor allem für Unternehmen bedeutende sicherheitstechnische Vorteile bieten.
![This is an image](https://upload.wikimedia.org/wikipedia/commons/6/67/Reverse_proxy_h2g2bob.svg)

### Squit
Squid ist das beliebteste Open-Source-Paket zum Erstellen eines Proxys in Ihrem selbst gehosteten Linux-Server und wird in diesem Projekt die Grundlage bilden

### Hardware
1. Raspberry pi
2. Memory Card (32 GB recommended)
3. Power Adapter
4. CAT 5 Cable connected to your Raspberry Pi and Router

## Preparation

### Updated

In erster Linie müssen wir sicherstellen, dass das OS auf dem aktuellsten stand ist, dies machen wir mit folgenden Komandos:

```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
```

### Statische IP-Adresse

Zuerst wird die statische IP-Addresse eingerichtet. Mit dem folgenden Befehl wird das Konfigurations-File angepasst:

`sudo nano /etc/network/interface`

Das File wird angpeasst:

```
auto eth0
allo-hotplug eth0
iface eth0 inet static
address 10.0.0.20
netmask 255.255.255.0
gateway 10.0.0.1
dns-nameserver 10.0.0.1
```

## Installation und Konfiguration von Squit

Die Squit-Software wird mit folgendem Komando heruntergeladen.

`sudo apt install squid`

Befor wir weiterfahren, sollten wir überprüfen ob der Squid-Server aktiv is.

`sudo systemctl status squid.service`

Von dem ursprüngliche Konfiguration-File wird zur Sicherheit ein Backup angelegt...

`cp /etc/squid/squid.conf /etc/squid/squid.conf.backup`

... und edditiert.

`sudo nano /etc/squid/squid.conf`

Folgende änderungen werden vorgenommen:

`Http_port: 3128 
Http_access deny all -> allow all`

Nach dem Konfigurationen Squid neustarten.

`sudo systemctl restart squid.service`
## Tests
