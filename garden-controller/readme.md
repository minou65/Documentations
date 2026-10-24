# Garden Controller

[Startseite](../readme.md) / Garden Controller

Der ESP32-GardenController (Garden Computer) steuert die Bewässerung im Garten
mit individuellen Zeitplänen für bis zu sechs Ventilzonen. Optional verhindern
zwei Bodenfeuchtesensoren die automatische Bewässerung, wenn der Boden bereits
ausreichend feucht ist.

## Funktionen

- Bis zu 6 Bewässerungszonen mit jeweils eigener Startzeit, Dauer und Wochentagen.
- Zeitpläne auch über Mitternacht hinweg.
- Bis zu 2 optionale Bodenfeuchtesensoren mit Kalibrierung und Schwellwerten.
- Zuordnung eines Sensors je Zone oder Betrieb ohne Feuchteprüfung.
- Manuelle Steuerung jeder Zone über Ein, Aus und Automatik.
- Bei manuellem Einschalten Rückkehr zur Automatik nach 30 Minuten.
- Weboberfläche für Status, Konfiguration und Firmware-Updates über WLAN.
- Optionale Zeitsynchronisation über NTP mit einstellbarer Zeitzone.

## Hardware

Die Steuerung basiert auf einem ESP32-Board mit acht Relais. Sechs Relais
schalten die Bewässerungszonen, die beiden übrigen versorgen die optionalen
Bodenfeuchtesensoren während der Messung.

Die Sensoren werden bei aktiviertem Betrieb nach dem Start und anschliessend
alle zwölf Stunden gemessen. Sie liefern damit keine kontinuierliche
Feuchteüberwachung. Ventile, Versorgung und Verdrahtung müssen zur verwendeten
Hardware passen; beachte die Anschluss- und Versorgungshinweise im Projekt.

**Hardware-Unterlagen:** [Übersicht und Anschlüsse](https://github.com/minou65/ESP32-GardenController#outputs-and-hardware)
| [Schaltungsunterlagen](https://github.com/minou65/ESP32-GardenController/tree/main/sch)
| [Bodenfeuchtesensoren](https://github.com/minou65/ESP32-GardenController#soil-moisture-sensors)
| [Gehäusedateien](https://github.com/minou65/ESP32-GardenController/tree/main/stl)

## Erste Schritte

1. **Hardware aufbauen:** Prüfe das Relaisboard, die Versorgung und die Verdrahtung der Ventile und optionalen Sensoren anhand der Projektanleitung.
2. **Firmware installieren:** Folge der Anleitung zur Erstprogrammierung des Relaisboards, beispielsweise mit einem ESP-Prog.
3. **Webzugang einrichten:** Verbinde dich beim ersten Start mit dem Access Point und öffne `http://192.168.4.1/config`. Richte WLAN und ein eigenes Passwort ein.
4. **Zeit einstellen:** Prüfe Uhrzeit und Zeitzone und aktiviere bei Bedarf NTP für die automatische Synchronisation.
5. **Sensoren und Zonen konfigurieren:** Kalibriere verwendete Sensoren und lege je Zone Name, Wochentage, Startzeit, Dauer und Sensorzuordnung fest. Eine Dauer von 0 deaktiviert den Zeitplan der Zone.
6. **Bewässerung testen:** Prüfe zuerst eine einzelne Zone und danach die Zeitpläne und die Feuchtesperre im Automatikbetrieb. Manuelles Ein und Aus übersteuern die Automatik.

## Dokumentation und Quellcode

- [Vollständige Projektanleitung](https://github.com/minou65/ESP32-GardenController#readme)
- [Erstprogrammierung des Relaisboards](https://github.com/minou65/ESP32-GardenController#flashing-the-relay-board-first-time)
- [Weboberfläche und Konfiguration](https://github.com/minou65/ESP32-GardenController#web-interface)
- [Inbetriebnahme und Fehlerbehebung](https://github.com/minou65/ESP32-GardenController#getting-started--troubleshooting)
- [Repository und Quellcode](https://github.com/minou65/ESP32-GardenController)

Die Projektanleitung ist die massgebliche Quelle für Anschlussbelegung,
elektrische Grenzwerte, Firmware und Konfigurationsparameter.

## Fragen und Fehler melden

Nutze die [GitHub-Issues des Garden Controllers](https://github.com/minou65/ESP32-GardenController/issues).
Nenne Board- und Firmwareversion, betroffene Zone, Zeitplan, Betriebsmodus
und gegebenenfalls Sensorkalibrierung und Feuchtewerte. Veröffentliche keine
WLAN-Passwörter oder anderen Zugangsdaten.
