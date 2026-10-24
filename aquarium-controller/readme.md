# Aquarium Controller

[Startseite](../readme.md) / Aquarium Controller

Der AquariumComputer ist eine ESP32-basierte Steuerung für Aquarienbeleuchtung
und -technik. Zeitgesteuerte Szenen legen die Helligkeit von drei Lichtkanälen
und den Zustand eines Relais fest, beispielsweise für ein CO2-Magnetventil.

## Funktionen

- 3 unabhängig steuerbare PWM-Kanäle für die Beleuchtung.
- 1 Relaisausgang für einen weiteren Verbraucher.
- Bis zu 15 Szenen mit Uhrzeit, Helligkeit je Kanal und Relaiszustand.
- Weiche Überblendungen zwischen Szenen oder sofortige Wechsel per Jump-Option.
- Szenenübergänge auch über Mitternacht hinweg.
- Manuelle Steuerung der Ausgänge über Ein, Aus und Automatik in der Weboberfläche.
- WLAN-Konfiguration, NTP-Zeitsynchronisation und einstellbare Zeitzone.
- Firmware-Updates über WLAN bei bereits installierter passender Firmware.

## Hardware

Die Steuerung verwendet ein ESP32-Board mit einem Relaisausgang und drei
externen MOSFET-Leistungsmodulen für die PWM-Lichtkanäle. Eine typische
Belegung sind Pflanzenlicht, Tageslicht und Mondlicht sowie ein CO2-Magnetventil
am Relais.

Netzteil, Leitungsquerschnitte, Kühlung und Gehäuse müssen zur tatsächlichen
Last und zur Umgebung am Aquarium passen. Prüfe die elektrischen Grenzwerte
der eingesetzten Komponenten anhand der Projektanleitung. Beachte insbesondere
die Hinweise zu Feuchtigkeit und zum Umgang mit Netzspannung.

**Hardware-Unterlagen:** [Komponenten und Aufbauhinweise](https://github.com/minou65/AquariumComputer#hardware)
| [Schaltungsunterlagen](https://github.com/minou65/AquariumComputer/tree/main/sch)

## Erste Schritte

1. **Hardware aufbauen:** Prüfe Versorgung, PWM-Module, Relais und Verbraucher anhand der Projektanleitung.
2. **Firmware installieren:** Richte die benötigten ESP32-Bibliotheken ein und folge den Build- und Upload-Hinweisen des Projekts.
3. **Webzugang einrichten:** Verbinde den Controller mit deinem WLAN beziehungsweise nutze seinen Access Point. Lege ein eigenes Passwort fest.
4. **Zeit einstellen:** Konfiguriere NTP-Server und Zeitzone und prüfe die angezeigte Uhrzeit.
5. **Szenen konfigurieren:** Lege Uhrzeiten, Helligkeiten und Relaiszustände fest. Wähle zwischen Überblendung und sofortigem Wechsel.
6. **Ausgänge testen:** Prüfe die Lichtkanäle und das Relais einzeln. Stelle sie anschliessend auf Automatik und kontrolliere den Szenenablauf, auch über Mitternacht.

## Dokumentation und Quellcode

- [Vollständige Projektanleitung](https://github.com/minou65/AquariumComputer#readme)
- [Konfiguration und Szenen](https://github.com/minou65/AquariumComputer#konfiguration)
- [Beispielkonfiguration](https://github.com/minou65/AquariumComputer#beispielkonfiguration)
- [Weboberfläche und manuelle Steuerung](https://github.com/minou65/AquariumComputer#web-interface)
- [Software, Bibliotheken und Upload](https://github.com/minou65/AquariumComputer#software)
- [Repository und Quellcode](https://github.com/minou65/AquariumComputer)

Die Projektanleitung ist die massgebliche Quelle für Anschlussbelegung,
elektrische Grenzwerte, Firmware und Konfigurationsparameter.

## Fragen und Fehler melden

Nutze die [GitHub-Issues des AquariumComputers](https://github.com/minou65/AquariumComputer/issues).
Nenne Board- und Firmwareversion, betroffenen Ausgang, Szeneneinstellungen,
Betriebsmodus sowie Uhrzeit und Zeitzone. Veröffentliche keine WLAN-Passwörter
oder anderen Zugangsdaten.
