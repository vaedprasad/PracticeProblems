## Electrical Problems

### Devices

Different electrical devices consume different amounts of power at different currents and voltages.  A battery has a voltage and an arbitrary capacity in amp-hours.  Create a `Device` class that represents an electrical device, and a `Battery` class that represents a battery.  `Device` should store its current, voltage, and power with accessor methods for each, while `Battery` should have a voltage and charge, each too with accessor methods.

### Power Consumption

Next, write a `void addDevice(Device device, double hours)` method in the `Battery` class that attatches a device to the battery for a certain amount of time.  Obviously this should decrement the battery charge, but not necesarily linearly: pay attention to devices and batteries of different voltages.  For example, a 5 Amp draw for an hour at 5 volts will decrement charge less than a 5 amp draw for an hour at 12 volts.  This simulation assumes that devices of different voltages will have a 100% efficient voltage regulator between them.

### Efficiency

Finally, write a `void addDevice(Device device, double hours, double efficiency)` method in the `Battery` class that accounts for inefficient voltage regulation.  Efficiency is a double ranging from 0-1, and should be overridden as 1 if the device and battery voltage are identical (as no voltage regulator is required).
