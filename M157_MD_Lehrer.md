# *Modul 157 Dokumentation für den Lehrer* 

# Inhaltsverzeichnis
  - [01 - Autoren](#01---autoren)
  - [02 - Funktion des Servers](#02---funktion des servers)
	- [02.1 - Beschreibung; welche Funktionen wird der Server erfuellen](#02.1---beschreibung; welche funktionen wird der server erfuellen)
  - [03 - Benötigte Hard- und Software](#03---benoetigte hard- und software)
	- [03.1 - Hardware](#03.1---Hardware)
	- [03.2 - Software](#03.2---Software)
  - [04 - Installationsanleitung](#04---installationsanleitung)
  - [05 - Testing](#05---Testverfahren)
  - [06 - Uebergabe an den Betrieb:](#06---uebergabe an den betrieb:)
  - [07 - Quellen](#07---quellen)

## 01 - Autoren

Autoren: Altin Nuhiu, Kerim Cetin


## 02 - Funktion des Servers

Die Kläranlage Zürich braucht für ihre EDV-Infrastruktur ein Monitoring-System. Sie haben unzählige Sensoren für die Wasserbecken im Einsatz die dazu benötigt werden, den Wasserstand 24/7 zu messen. Zusätzlich möchte der IT-Leiter der Kläranlage Zürich die ganze EDV-Infrastruktur überwachen lassen.


## 03 - Benötigte Hard- und Software

### 03.1 - Hardware

* Raspberry Pi
* MicroSD-Karte 
* Netzteil
* Netzwerk-Kabel

### 03.2 - Software

- Betriebssystem [NEMS Linux]( https://nemslinux.com/download/nagios-for-raspberry-pi-4.php ) 
- Nagios Monitoring (Im NEMS Linux schon vorhanden)

- [NSClient]( https://nsclient.org/download/ ) / NRPE

## 04 - Installationsanleitung

### Basis Konfigurationen

Den Raspberry mit NEMS Linux aufsetzen.  Nach der Erfolgreichen Installation ist das Nems Monitoring Portal über den Browser erreichbar.

### ![Client aufnehmen.png](https://github.com/Altinnn/M157/blob/master/Bilder/Nems%20Portal.png)





### NEMS Monitoring Einrichten

Nems Server überprüfen ob alle Funktionen und Service installiert worden sind. Dies kann im Browser unter **Nems Server Overview** angezeigt werden. 


### ![Client aufnehmen.png](https://github.com/Altinnn/M157/blob/master/Bilder/Nems%20Server%20Overview.png)



### Client / Server im Monitoring aufnehmen

Im NEMS Configurator die gewünschten Geräte hinzufügen. Diese

erfolgt unter **Basic Items -> Add Host**.  Nun die IP Adresse, DNS Name hinzufügen und die entsprechende Services auswählen die überwacht werden sollen z.B Drive Space, Memory Usage, Uptime, PING, CPU Load etc. 



### ![Client aufnehmen.png](https://github.com/Altinnn/M157/blob/master/Bilder/Client%20aufnehmen.png)



### NSClient/ **NRPE** Installation

Damit Nagios Daten von dem überwachendem Geräte erhalten kann muss ein Add-in installiert werden. Unter Windows wird der NSCLient benötigt entsprechend. Diese Add-in kann auf der NSClient Webseite heruntergeladen werden.  Da die Installation Click to Run ist wird diese nicht weiter erläutert. 

Wenn Jedoch z.B eine Ubuntu Maschinen überwacht werden soll wird NRPE ( **Nagios Remote Plugin Executor**) benötigt. Diese wie folgt installieren 

```
sudo apt-get update
sudo apt-get install nagios-nrpe-server nagios-plugins
```

Nach dem das Plugin Installiert ist muss noch der Monitoring Server hinzugefügt werden.  Diese im Config File **/etc/nagios/nrpe.cfg**  hinzufügen

```
 allowed_hosts=127.0.0.1, 192.168.1.100
```



Nun die Verbindung mit dem Monitoring Server Verifiziere. 

```
check_nrpe -H 192.168.1.11

NRPE v2.15
```



Zum Schluss noch den Service neu starten. 

```
sudo /etc/init.d/nagios-nrpe-server stop
sudo /etc/init.d/nagios-nrpe-server start
sudo /etc/init.d/nagios-nrpe-server restart
```

## 05 - Testing

| Nr.  | SOLL                                                         | Vorgehensweise                                               | Erfüllt   |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ | --------- |
| 1    | Neuste Version vom NEMS ist auf dem Raspberry installiert    | Neuste Version auf der Offiziellen Seite herunterladen       | Ja        |
| 2    | Nems Server überprüfen ob alle Funktionen und Service installiert worden sind | Dies kann im Browser unter **Nems Server Overview** angezeigt werden | Ja        |
| 3    | Nems Monitoring Server kann über den Browser aufgerufen werden. | Über den Browser mit der entsprechende IP-Adresse auf das Nems Portal verbinden | Ja        |
| 4    | NSClient/ **NRPE** senden Daten an den Monitoring Server.    | Nagios Dashboard                                             | teilweise |
| 5    | Clients / Server sind im Nagios Monitrong hinzugefügt        | Erscheinen im Nems Konfigurator als zu Überwacheden Geräte   | Ja        |
| 6    |                                                              |                                                              |           |



## 06 - Übergabe an den Betrieb:

Ist ein einem separaten Abnahmeprotokoll festgehalten. 

## 07 - Quellen

- https://nemslinux.com/

- https://www.nagios.org/

- https://nsclient.org/
- https://docs.nsclient.org/installing/ 

- https://docs.nemslinux.com/ 
