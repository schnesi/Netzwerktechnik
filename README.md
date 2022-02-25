# Squit Proxyserver

## Ausgangslage

In unserem Praktikum haben wir ein Netzwerk aufgebaut. Dieses enthilt zwei Firewalls, ein DNS-, ein Proxy-, ein DHCP-Server, ein RADIUS und drei Zugangspunkte. Unsere Aufgabe war, den Proxyserver einzurichten.

## Intro

Ein Proxy bzw. ein Proxy-Server ist ein Vermittler innerhalb eines Netzwerks. Er wird zwischen Nutzer und Netzwerk-Ressource geschaltet. Nutzer, die ins Internet gehen und einen Proxy nutzen, nehmen also einen Umweg. Durch diesen Umweg kann unter anderem die Kommunikation zwischen Nutzer und Netzwerk-Ressource abgesichert, verschleiert oder beschleunigt werden. Neben den Funktionen von Standard-Proxys gibt es auch Reverse-Proxys, die vor allem für Unternehmen bedeutende sicherheitstechnische Vorteile bieten.

## Installation und Konfiguration

Zuerst wird die statische IP-Addresse eingerichtet:
`sudo nano /etc/network/interface`
