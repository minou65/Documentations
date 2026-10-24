# Modellbahn-Decoder

[Startseite](../readme.md) / Modellbahn

Zentrale Einstiegsseite zu meinen DCC-Decoder-Projekten für die Modellbahn.
Hier findest du eine Auswahlhilfe sowie Links zu Anleitungen, Hardware,
Konfiguration und Quellcode.

## Inhalt

- [Projektübersicht](#projektübersicht)
- [zDecoder](#zdecoder)
- [cDecoder](#cdecoder)
- [KirmesKontroller](#kirmeskontroller)
- [Erste Schritte](#erste-schritte)
- [Fragen und Fehler melden](#fragen-und-fehler-melden)

## Projektübersicht

| Projekt | Einsatz | Hardware und Ausgänge | Konfiguration |
| --- | --- | --- | --- |
| [zDecoder](#zdecoder) | Schalten, Beleuchtung, Lichteffekte, Weichen und Servos | ESP32 NodeMCU, bis zu 16 Ausgänge | Weboberfläche über WLAN |
| [cDecoder](#cdecoder) | Ein/Aus-, Impuls- und Blinkfunktionen | ATtiny85, bis zu 5 Ausgänge | DCC-Konfigurationsvariablen (CVs) |
| [KirmesKontroller](#kirmeskontroller) | Kirmesmodelle und Karussells mit Licht, Bewegung und Sound | ESP32-S3, 8 digitale Ausgänge und 3 Servo-Ausgänge | Weboberfläche über WLAN |

**Welcher Decoder passt?** Für vielseitige Schalt- und Lichteffekte ist der
zDecoder der Einstieg. Für kompakte Funktionsanwendungen mit CV-Konfiguration
eignet sich der cDecoder. Für Kirmesmodelle mit Sound und Bewegungsabläufen
ist der KirmesKontroller vorgesehen.

## zDecoder

Der zDecoder ist ein DCC-Decoder auf Basis eines ESP32 NodeMCU. Er wird über
DCC oder die Weboberfläche gesteuert und kann einen eigenen WLAN-Access-Point
bereitstellen oder in ein bestehendes WLAN eingebunden werden.

- Bis zu 16 Ausgänge für unterschiedliche Anwendungen.
- Lichteffekte wie Blinker, Wechselblinker, Schweisslicht, Feuer und Lauflicht.
- Betriebsarten für Hausbeleuchtung, Weichen, Entkuppler und Servos.
- Konfiguration im Browser und Firmware-Updates über WLAN.

**Dokumentation:** [Übersicht und Inbetriebnahme](https://github.com/minou65/DCC_zDecoder#readme)
| [Betriebsarten](https://github.com/minou65/DCC_zDecoder/tree/main/doc)
| [Schaltungsunterlagen](https://github.com/minou65/DCC_zDecoder/tree/main/sch)
| [Firmware-Releases](https://github.com/minou65/DCC_zDecoder/releases)
| [Quellcode](https://github.com/minou65/DCC_zDecoder)

## cDecoder

Der cDecoder ist ein DCC-Funktionsdecoder auf Basis eines ATtiny85. Die
Ausgänge und ihre Zuordnung zu den Funktionstasten werden über CVs eingestellt.

- Bis zu 5 Ausgänge mit Ein/Aus-, Impuls- und Blinkfunktion.
- Dimmen der Ausgänge AUX 1 und AUX 2.
- Einstellbare Blinkzeiten und automatisches Abschalten.
- Analogbetrieb, konfigurierbare dauerhaft aktive Ausgänge und Anschluss eines externen Powerpacks.

**Dokumentation:** [Anleitung und Anschlüsse](https://github.com/minou65/DCC_cDecoder#readme)
| [CV-Tabelle](https://github.com/minou65/DCC_cDecoder#cv-tabelle)
| [Konfigurationsbeispiele](https://github.com/minou65/DCC_cDecoder#beispiele)
| [Schaltungsunterlagen](https://github.com/minou65/DCC_cDecoder/tree/main/sch)
| [Quellcode](https://github.com/minou65/DCC_cDecoder)

## KirmesKontroller

Der KirmesKontroller (kDecoder) ist ein DCC-Decoder für Kirmes- und
Karussell-Anwendungen auf Basis des YB-ESP32-S3-AMP. Er verbindet die Steuerung
von Beleuchtung und Bewegung mit der Wiedergabe von Sounddateien.

- 8 digitale Ausgänge, 3 Servo-Ausgänge und 2 digitale Eingänge.
- Soundwiedergabe von SD-Karte über I2S-Audio.
- Steuerung über DCC, Weboberfläche sowie lokale Taster und Sensoren.
- Konfigurierbare Aktionsketten und Sequenzen sowie Firmware-Updates über WLAN.

**Dokumentation:** [Übersicht und Hardware](https://github.com/minou65/DCC_kDecoder_KirmesDecoder#readme)
| [System und WLAN](https://github.com/minou65/DCC_kDecoder_KirmesDecoder/blob/main/doc/SystemConfiguration.md)
| [Sound](https://github.com/minou65/DCC_kDecoder_KirmesDecoder/blob/main/doc/Soundhandling.md)
| [Servos](https://github.com/minou65/DCC_kDecoder_KirmesDecoder/blob/main/doc/Servohandling.md)
| [Ausgänge und Lichteffekte](https://github.com/minou65/DCC_kDecoder_KirmesDecoder/blob/main/doc/LEDhandling.md)
| [Ampelsteuerung](https://github.com/minou65/DCC_kDecoder_KirmesDecoder/blob/main/doc/TrafficLighthandling.md)
| [Quellcode](https://github.com/minou65/DCC_kDecoder_KirmesDecoder)

## Erste Schritte

1. **Projekt auswählen:** Vergleiche den Einsatzzweck und die benötigten Ausgänge in der [Projektübersicht](#projektübersicht).
2. **Hardware prüfen:** Lies die Anschluss- und Versorgungshinweise des jeweiligen Projekts. Beachte Platinenversion, Ausgangsbelastbarkeit und gegebenenfalls notwendige Hardware-Anpassungen.
3. **Firmware aufspielen:** Folge der projektspezifischen Anleitung. Der cDecoder wird per ISP programmiert; zDecoder und KirmesKontroller unterstützen WLAN-Updates bei bereits installierter passender Firmware.
4. **Decoder konfigurieren:** Richte beim zDecoder und KirmesKontroller WLAN und Weboberfläche ein. Beim cDecoder erfolgt die Konfiguration über CVs.
5. **Funktionen testen:** Prüfe zuerst eine einzelne Funktion, bevor du weitere Verbraucher und Abläufe einrichtest.

Die verlinkten Projekt-Dokumentationen sind die massgebliche Quelle für
Anschlussbelegung, elektrische Grenzwerte, Firmware und Konfigurationsparameter.
Diese Seite bündelt die Einstiege, ohne die technischen Anleitungen zu duplizieren.

## Fragen und Fehler melden

Bitte melde Fragen, Fehler oder Erweiterungswünsche beim passenden Projekt:

- [zDecoder: Issues](https://github.com/minou65/DCC_zDecoder/issues)
- [cDecoder: Issues](https://github.com/minou65/DCC_cDecoder/issues)
- [KirmesKontroller: Issues](https://github.com/minou65/DCC_kDecoder_KirmesDecoder/issues)

Nenne dabei nach Möglichkeit die Platinen- und Firmwareversion, die verwendete
DCC-Zentrale und die Schritte, mit denen sich das Verhalten nachvollziehen lässt.
