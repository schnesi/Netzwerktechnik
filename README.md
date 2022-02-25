# Squit Proxyserver

## Ausgangslage

In unserem Praktikum haben wir ein Netzwerk aufgebaut. Dieses enthilt zwei Firewalls, ein DNS-, ein Proxy-, ein DHCP-Server, ein RADIUS und drei Zugangspunkte. Unsere Aufgabe war, den Proxyserver einzurichten.

## Intro

Ein Proxy bzw. ein Proxy-Server ist ein Vermittler innerhalb eines Netzwerks. Er wird zwischen Nutzer und Netzwerk-Ressource geschaltet. Nutzer, die ins Internet gehen und einen Proxy nutzen, nehmen also einen Umweg. Durch diesen Umweg kann unter anderem die Kommunikation zwischen Nutzer und Netzwerk-Ressource abgesichert, verschleiert oder beschleunigt werden. Neben den Funktionen von Standard-Proxys gibt es auch Reverse-Proxys, die vor allem für Unternehmen bedeutende sicherheitstechnische Vorteile bieten.

## Statische IP-Adresse

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

Die Squit-Software wird mit 

`sudo apt install squid`

heruntergeladen.
Von dem ursprüngliche Konfiguration-File wird zur Sicherheit ein Backup angelegt.

`cp /etc/squid/squid.conf /etc/squid/squid.conf.bachup`
