# Low Current RTC Breakout With Super Capacitor Backup

This breakout is based on the [DS3231](docs/DS3231.pdf) RTC from Maxim Integrated and a [FT0H474ZF](docs/FT0H474ZF.pdf) 0.47F super capacitor from Kemet.

The design powers the DS3231 via the V<sub>bat</sub> input rather than V<sub>cc</sub>, this results in a current consumption of ~3uA, with spikes to 575uA every 65 seconds when temperature conversion occurs (see p3 of the data sheet).

![Schematic](rtc-ds3231-schematic.png)
