# Low Current RTC Breakout With Super Capacitor Backup

<img src="rtc-ds3231-breakout.jpg" width="200">

This 32x21mm breakout is based on the [DS3231](docs/DS3231.pdf) Real Time Clock (RTC) from Maxim Integrated and a [FT0H474ZF](docs/FT0H474ZF.pdf) 0.47F super capacitor from Kemet for backup power.

The design powers the DS3231 via the V<sub>bat</sub> input rather than V<sub>cc</sub>, this results in a current consumption of ~3uA, with spikes to 575uA every 65 seconds when temperature conversion occurs. See the electrical characteristics for V<sub>cc</sub> = 0V, V<sub>bat</sub> = 2.3V to 5.5V on page 3 of the data sheet.

## Design Information

![Schematic](rtc-ds3231-schematic.png)

* The schematic shows a DS3231SN which operates accurately below freezing, but the DS3131S can be used if the device is used at room temperature.
* The [BAT54H](docs/BAT54H.pdf) Schottky diode prevents the super capacitor from powering the connected MCU. It has a forward current of 200mA to allow for the current to charge the super capacitor.
* R3 has been chosen to limit the super capacitor charge current to ~150mA based on V<sub>bat</sub> being 3.3V. If the input voltage is higher a correspondingly larger value will be required to maintain the maximum current of 150mA.

## PCB

The design files can be found at [https://oshwlab.com/chrisb2/ds3231-low-power](https://oshwlab.com/chrisb2/ds3231-low-power) and the Gerbers are included in this repository.

![PCB](rtc-ds3231-pcb.png)

## BOM

| Designator | Value | Part |
|------|-------|----------|
| - | DS3231SN | 1 |
| C1 | FT0H474ZF 0.47F | 1 |
| C2 | 0.1uF | 1 |
| R1/R2 | 4.7k | 2 |
| R3 | 15 (500mW) | 1|
| D1 | BAT54H | 1|
