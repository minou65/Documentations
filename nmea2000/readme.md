# NMEA 2000

[Startseite](../readme.md) / NMEA 2000

Meine Projekte zum Erfassen von Messwerten und zum Schalten von Verbrauchern
an Bord über einen NMEA-2000-Bus. Diese Seite hilft bei der Projektauswahl und verlinkt die jeweiligen
Anleitungen und Hardware-Unterlagen.

Der zentrale Hardware-Einstieg für alle NMEA-Projekte ist das
[SensorBoard](#sensorboard). Bestückung, Sensoranschlüsse und gegebenenfalls
abweichende Hardware sind in den jeweiligen Projektanleitungen beschrieben.

## Projektübersicht

| Projekt | Einsatz | Besonderheiten |
| --- | --- | --- |
| [BatteryMonitor](#batterymonitor) | Batterieüberwachung | Spannung, Strom, Ladezustand und geschätzte Restlaufzeit |
| [DS1820](#ds1820) | Temperaturüberwachung | Bis zu 4 Sensoren und konfigurierbare Alarme über den Bus |
| [BME280](#bme280) | Umgebungsklima | Temperatur, Luftfeuchte und Luftdruck |
| [FluidLevel](#fluidlevel) | Tankfüllstand | Resistiver Tankgeber; weitere Sensorvarianten in eigenen Branches |
| [SensorBoard](#sensorboard) | Zentraler Hardware-Einstieg für alle NMEA-Projekte | Schaltplan, Platine, Stückliste und Anschlussbelegungen |
| [Relaybox](#relaybox) | Verbraucher schalten | Bis zu 8 Relais, Bus- und Websteuerung |

## BatteryMonitor

Der BatteryMonitor erfasst Batteriespannung und Strom mit einem INA226 und
ermittelt daraus anhand der konfigurierten Batterieparameter den geschätzten
Ladezustand (SoC) und die Restlaufzeit.

- Messwerte über NMEA 2000 und eine Weboberfläche.
- Anzeige von Temperatur und Batteriestatistiken.
- Konfiguration von Batterie, Shunt und Kalibrierung im Browser.

**Links:** [Anleitung](https://github.com/minou65/NMEA2000-BatteryMonitor#readme)
| [Hardware](https://github.com/minou65/NMEA2000-BatteryMonitor/tree/main/sch)
| [Releases](https://github.com/minou65/NMEA2000-BatteryMonitor/releases)
| [Repository](https://github.com/minou65/NMEA2000-BatteryMonitor)
| [Issues](https://github.com/minou65/NMEA2000-BatteryMonitor/issues)

## DS1820

Temperaturüberwachung mit bis zu vier DS1820-Sensoren. Für jeden Sensor
lassen sich Temperaturquelle und Alarmbedingungen konfigurieren.

- Übertragung von Temperaturen sowie Temperatur- und Fehleralarmen über NMEA 2000.
- Konfigurierbare Grenzwerte und zeitweises Stummschalten von Alarmen.
- Weboberfläche für Messwerte, Konfiguration und Firmware-Updates.

**Hardware-Hinweis:** Bei SensorBoard v3 muss die DS1820-Datenleitung laut
Projektanleitung von IO36 getrennt und mit IO22 verbunden werden.

**Links:** [Anleitung und Hardware-Hinweise](https://github.com/minou65/NMEA2000-DS1820#readme)
| [Releases](https://github.com/minou65/NMEA2000-DS1820/releases)
| [Repository](https://github.com/minou65/NMEA2000-DS1820)
| [Issues](https://github.com/minou65/NMEA2000-DS1820/issues)

## BME280

Umgebungssensor für Temperatur, relative Luftfeuchtigkeit und Luftdruck
auf Basis eines BME280. Zusätzlich werden Taupunkt und gefühlte Temperatur
berechnet.

- Übertragung der Messwerte über NMEA 2000.
- Konfigurierbare Temperatur- und Feuchtequelle.
- Live-Anzeige, Konfiguration und Firmware-Updates über die Weboberfläche.

**Links:** [Anleitung und Sensoranschluss](https://github.com/minou65/NMEA2000-BME280#readme)
| [Gehäuse](https://github.com/minou65/NMEA2000-BME280/tree/main/stl)
| [Releases](https://github.com/minou65/NMEA2000-BME280/releases)
| [Repository](https://github.com/minou65/NMEA2000-BME280)
| [Issues](https://github.com/minou65/NMEA2000-BME280/issues)

## FluidLevel

Tankfüllstandsmessung mit Übertragung über NMEA 2000. Der Hauptbranch
verwendet einen resistiven Tankgeber mit 240 Ohm bei leerem und 33 Ohm bei
vollem Tank; die Werte lassen sich kalibrieren.

- Konfigurierbarer Tanktyp und Tankinhalt.
- Messwertglättung sowie Erkennung von Leitungsunterbrechung und Kurzschluss.
- Live-Anzeige, Kalibrierung und Firmware-Updates im Browser.
- Separate Branches für die Sensorvarianten VL53L0X und VL53L1X.

**Links:** [Anleitung und Hardware](https://github.com/minou65/NMEA2000-FluidLevel#readme)
| [Sensorvarianten / Branches](https://github.com/minou65/NMEA2000-FluidLevel/branches)
| [Releases](https://github.com/minou65/NMEA2000-FluidLevel/releases)
| [Repository](https://github.com/minou65/NMEA2000-FluidLevel)
| [Issues](https://github.com/minou65/NMEA2000-FluidLevel/issues)

## SensorBoard

Zentrale Hardware-Dokumentation meiner NMEA-Projekte. Die universelle
Sensorplatine basiert auf einem ESP32 D1 Mini und einem MCP2562-CAN-Transceiver.
Je nach Projekt werden unterschiedliche Komponenten und Anschlüsse bestückt.

- Schaltplan, Platinenlayout und Stückliste.
- Anschlussbelegungen für Versorgung, CAN-Bus, DS1820- und I2C-Sensoren.
- Bestückungsvarianten für DS1820, BME280, FluidLevel und BatteryMonitor.
- Hinweise zu Versorgung, NMEA-Steckerbelegung und sicherer Installation.

Zusätzliche Sensoren, Shunts, Sicherungen und Gehäuse richten sich nach dem
jeweiligen Projekt. Die Relaybox verwendet laut ihrer Anleitung ein eigenes
ESP32-Relaisboard; dessen Schaltungsunterlagen sind im Relaybox-Projekt verlinkt.

**Links:** [Hardware-Übersicht und Anschlüsse](https://github.com/minou65/NMEA2000-SensorBoard#readme)
| [Schaltplan](https://github.com/minou65/NMEA2000-SensorBoard/blob/main/NMEA-Sensorboard.sch)
| [Platinenlayout](https://github.com/minou65/NMEA2000-SensorBoard/blob/main/NMEA-Sensorboard.brd)
| [Stückliste](https://github.com/minou65/NMEA2000-SensorBoard#part-list)
| [Repository](https://github.com/minou65/NMEA2000-SensorBoard)
| [Issues](https://github.com/minou65/NMEA2000-SensorBoard/issues)

## Relaybox

Relaissteuerung auf Basis eines ESP32-Relaisboards mit CAN-Anbindung über
MCP2562. Je nach Board stehen zwei oder bis zu acht Relais zur Verfügung.

- Schalten über NMEA 2000 oder direkt in der Weboberfläche.
- Einstellbare automatische Abschaltzeit pro Relais.
- Zusammenarbeit mit Plottern, die PGN 127501 und 127502 unterstützen.
- Schaltungsunterlagen und druckbares Gehäuse im Projekt-Repository.

**Links:** [Anleitung und Hardware](https://github.com/minou65/NMEA2000-Relaybox#readme)
| [Schaltungsunterlagen](https://github.com/minou65/NMEA2000-Relaybox/tree/main/sch)
| [Gehäuse](https://github.com/minou65/NMEA2000-Relaybox/tree/main/stl)
| [Repository](https://github.com/minou65/NMEA2000-Relaybox)
| [Issues](https://github.com/minou65/NMEA2000-Relaybox/issues)

## Erste Schritte

1. **Projekt auswählen:** Bestimme Messgrösse oder Schaltaufgabe anhand der Projektübersicht.
2. **Hardware prüfen:** Beginne beim [SensorBoard](#sensorboard) und beachte Boardversion, Bestückung, Sensorvariante, Versorgung und Anschlussbelegung in der jeweiligen Projektanleitung. Beim FluidLevel muss der Branch zum Sensor passen.
3. **Firmware installieren:** Nutze die Build- und Installationshinweise des ausgewählten Projekts.
4. **Konfigurieren:** Richte den Webzugang ein, ändere Standardpasswörter und stelle die projektspezifischen Instanzen, Quellen und Kalibrierwerte ein.
5. **Integration testen:** Prüfe Messwerte, Alarme oder Schaltfunktionen und die Unterstützung der benötigten PGNs durch deinen Plotter.

## Hinweise zum Betrieb

Die Bezeichnung NMEA 2000 allein bedeutet keine Zertifizierung. Das
FluidLevel-Projekt weist ausdrücklich darauf hin, dass Hard- und Software
nicht zertifiziert sind und der Anschluss auf eigene Verantwortung erfolgt.
Beachte die Hinweise des jeweiligen Projekts und prüfe die Kompatibilität
mit deinem Bordnetz.

Bei Arbeiten an Batterien und Verbrauchern sind die Schutz- und
Versorgungshinweise der Projektanleitungen zu beachten. Der BatteryMonitor
verlangt insbesondere eine Sicherung in der Plusleitung von der Batterie zum
Sensor und einen passend dimensionierten Shunt.

## Fragen und Fehler melden

Nutze den Issues-Link beim jeweiligen Projekt. Hilfreich sind Board- und
Firmwareversion, Sensorvariante, Konfiguration, betroffene PGNs, verwendeter
Plotter und Schritte zum Nachstellen des Verhaltens. Keine Passwörter oder
anderen Zugangsdaten veröffentlichen.
