# *Modul 157 Dokumentation für die Lernenden* 

# Inhaltsverzeichnis
  - [01 - Autoren](#01---autoren)
  - [02 - Einfuehrung](#02---einfuehrung)
	- [02.1 - Funktionialitaet](#02.1---funktionalitaet)
  - [03 - Materialliste](#03---materialliste)
	- [03.1 - Verwendetet-Tools](#02.1---verwendete-tools)
  - [04 - Installationsanleitung](#04---installationsanleitung)
	- [04.1 - Anweisung verstaendlich und nachvollziehbar](#04.1---anweisung verstaendlich und nachvollziehbar)
	- [04.2 - Keine fertigen Loesungsschritte aufzeigen](#04.2---keine fertigen loesungsschritte aufzeigen)
	- [04.3 - Hilfestellung](#04.3---hilfestellung)
  - [05 - Qualitaetskontrolle](#05---qualitaetskontrolle)
  - [06 - Error-Handling](#06---error-handling)

## 01 - Autoren

Autoren: Altin Nuhiu, Kerim Cetin


## 02 - Einführung

### 02.1 - Auftrag

Die Kläranlage Zürich braucht für ihre EDV-Infrastruktur ein Monitoring-System. Sie haben unzählige Sensoren für die Wasserbecken im Einsatz die dazu benötigt werden, den Wasserstand 24/7 zu messen. Zusätzlich möchte der IT-Leiter der Kläranlage Zürich die ganze EDV-Infrastruktur überwachen lassen.



### Vorgehensweise

- Rasberry PI mit NEMS Linux aufsetzten 
- Grundkonfiguration Betriebssystem vornehmen
- Nagios Enterprise Monitoring Server installieren
- Clients oder Server ins Monitoring einbinden
- Email Benachrichtigung einrichten



### Zeitaufwand

Der Zeitrahmen für diese Aufträge beträgt 3 Schullektionen.  

## 03 - Materialliste
* Raspberry Pi
* MicroSD-Karte 
* Netzteil
* Netzwerk-Kabel

### 03.1 - Verwendetet Tools
* Git-Client (SSH-Key)
* IP-Scanner 
* Notepad ++
* Linux NEMS Image

## 04 - Installationsanleitung

### Auftrag

Für dieses Projekt soll die Monitoring Lösung [Nagios]( https://www.nagios.org/ ) realisiert werden. Dies wird über das Betriebssystem [NEMS Linux]( https://nemslinux.com/download/nagios-for-raspberry-pi-4.php ) auf dem Raspberry Pi installiert und konfiguriert. Dazu sollen verschiedene Geräte im Netzwerk Überwacht werden  wie z.B. Client, Server Access Point, Router usw. Ausserdem soll die Email Benachrichtigung aktiviert werden damit sie immer bescheid wisse was in Ihrer IT-Infrastruktur abgeht.   

- Den Raspberry Pi mit NEMS Linux als OS aufsetzen
- Sich mit der Monitoring Lösung Nagios vertraut machen 
- Die zu überwachenden Geräte (mindestes 3 Geräte) ins Nagios Monitoring einbinden 
- Email Notification einrichten
- Monitoring Testen

### Hilfestellung

Wenn Hilfe benötigt wird kann diese auf den Foren von NEMS Linux und Nagios gefunden werden.



## 05 - Qualitätskontrolle

#### Nems Linux Funktionalität

SOLL: Nagios Monitoring Server kann über den Browser aufgerufen werden.

#### Nagios Monitoring Server

SOLL: Zu überwachende Geräte können hinzugefügt werden. 

#### NSClient / NRPE

SOLL: Monitoring Daten werden an Monitoring Server übermittelt.

#### Monitoring

SOLL: Nagios bereitet entsprechende Daten auf und zeigt diese im Dashboard dar.  

## 06 - Error-Handling

Auf der Webseite von NEMS Linux und Nagios sind Hilfreiche Erklärungen. Natürlich gibt es auch im World Wide Web unzählige Foren bezüglich Monitoring mit NEMS/Nagios. 
