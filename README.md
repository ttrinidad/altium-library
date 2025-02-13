# Celestial Altium Library

An exceptional, open source database library for Altium, currently supporting MSSQL and SQL Azure as the backend for easy use within teams, and no data corruption unlike MS Access.


This library has been built for high quality data, with high quality footprints and high quality 3D models.

Join us on [Discord](https://discord.gg/MEQ5Xe5) to chat.

# Database Access
You can register for free access on the [Altium Library Portal](http://portal.altiumlibrary.com/Identity/Account/Login). 

The library is still being rebuilt on the new platform, it has over 85,000 components but is missing a lot of IC's which are being added back as fast as possible.

Check in with the community on [Discord Chat](https://discord.gg/MEQ5Xe5) for the latest, to get some help, or just to say hi!

# Why use an Altium DBLib over an Integrated Library?

Altium Database libraries make you design your schematic with the part you are going to use, rather than a generic part with the same footprint. Rather than selecting "RJ45 Jack" you instead select Amphenol Commercial Products part number RJCSE538001. This is reflected in your BOM - the entire BOM fills itself out, meaning no more trying to remember exactly what part you actually meant to put in there was, or what voltage that capacitor was.

Prior to using a DBLib, it would often take me half a day to fill out the bill of materials. I'd have to find each resistor on the supplier's website, list it down with the supplier's part number, manufacturer, manufacturer name, etc... Now I just generate the BOM in the output job, and everything is done. No more trying to remember "was that 33uF cap 25V or 50v?", or finding out after the fact that no, that capacitor isn't available as a 47uF 50V variant in that package, despite the fact you were sure it was!

Basically: You save time on the design, and you greatly reduce errors occurring from specifying a part you didn't actually use (who hasn't accidentally specified a right angle connector variant when it was really vertical on the board - oops?)

# The Library
### Why use this library over something like Ultra Librarian?
Ultra librarian doesn't have high quality 3d models or parametrics. If all you need is basic footprint, Ultra librarian is what you want. If you want something open source, ultra high quality parts and with all the data fields you desire.. then you'll probably really like this library.

If you're integrating your electronic design into a housing or designing injection moulded cases for it - you need accurate 3d models or your mechanical engineers will spend a lot of time making sure the case fits your design files.

### Data
All parts in the database are matched with every relevant parameter that Digi-Key has for the part, so you can search/filter within Altium for the part you require. If you are looking for low Rds(on) N-Ch fets, just add the Rds(on) column to the Altium library window and sort by it.

Every part has a link to the part on Digi-key, and has a link to the datasheet for the part for ease of design. Both the Digi-Key part number, price, and manufacturer name/part number are stored, now your BOM will be completely filled out automatically.

### Footprints
Every part has a footprint created to match it's manufacturers recommended footprint by the manufacturer, or lacking that, an IPC Compliant footprint for the manufacturers specific package sizing. There are no generic footprints within this library, everything is manufacturer specific. 

Every footprint has a high quality, dimensionally accurate, accurately coloured 3d model. For complex parts (connectors like modular jacks), the manufacturers model is preferred however is always fully coloured and checked for accuracy against their drawings and modified as required.  I've found issues with the accuracy of the manufacturer issued model from most models, where they do not match the datasheet - every instance has been checked with the manufacturer and many have re-issued their 3d models because of these checks.

Basic parts (TSSOP/SOP/Resistors etc) I have created every model from scratch in SolidWorks, if the manufacturers dimensions vary from the JEDEC standard, they receive their own version of the 3d model (see SOT-23-3..) For ultra basic parts with no features (QFN/DFN), a black basic Altium 3D extrusion is used of the correct size.

Every part's centre position is where the Pick and place head should grab the part. For companies running their own Pick and Place machine, this is very convenient compared to centres at pin 1/centre of pads - your pick and place export list now has centres in the correct location.

### Symbols 

Every symbol in the library is somewhat standardised as to where pins are located, such as VCC in the top left, GND in the bottom left, user function pins on the right (controllable inputs/outputs). Standard protocols like SPI have the pins in the same order in every part - however manufacturer datasheet labeling is kept (DOUT rather than MISO for example) to make it easier to reference the datasheet. All components within a database category should have similar if not identical layouts/pin groupings where possible. This makes it much easier to switch out components.

All passive components, such as resistors and capacitors all have the same size symbol lead span, keeping your schematics tidy.

# What components are contained in the library?
There are currently over 27000 parts in the library, this number sounds quite large but when you consider you need every value of resistor in 1%, 0.5%, 0.25%, 0.1% and 0.05%, in 0201, 0402, 0603, 0805 and 1206... you're now looking at over 5000 resistors.

Generally only SMT parts are in the library, except connectors, buttons and displays which have a mixture.

There are currently parts from over 120 manufacturers in the database.

##### Currently there are database views for:

 - ADC - Programmable
 - Audio - Amplifier
 - Battery Holder
 - Button - Push
 - Button - Slide
 - Button - Tactile
 - Capacitor - Aluminium
 - Capacitor - Aluminium Polymer
 - Capacitor - Aluminium Through hole
 - Capacitor - Ceramic
 - Capacitor - RF
 - Capacitor - Tantalum
 - Capacitor - Tantalum Polymer
 - Charger
 - Chip LED
 - Connector - Backplane
 - Connector - Barrier Block
 - Connector - Card Edge
 - Connector - Dev Board
 - Connector - Modular
 - Connector - Modular w/Magnetics
 - Connector - Rectangular
 - Connector - RF
 - Connector - SD
 - Connector - Terminal Block
 - Connector - USB
 - Digital Isolator
 - Digital to Analogue Converter
 - Diode - Rectifier
 - Diode - TVS
 - Ferrite Chip
 - Gate Driver
 - Inductor - Power
 - Inductor - RF
 - Interface - CAN
 - Interface - Ethernet
 - Interface - RS485
 - IR Receiver
 - LCD Display - Graphic
 - LED Driver
 - Light Pipe
 - MCU - ARM
 - MCU - AVR
 - Memory - EEPROM
 - Memory - FLASH
 - Motor Driver - Controller
 - Motor Driver - Stepper
 - Mounting Bracket
 - Multiplexer
 - N-Channel Dual FET Array
 - N-Channel FET
 - Optoisolators
 - Oscillator - Crystal
 - Oscillator - MEMS
 - Oscillator - TCXO
 - Oscillator - VCTCXO
 - Oscillator - XO
 - P-Channel Dual FET Array
 - P-Channel FET
 - Power Module
 - Reset Supervisor
 - Resistor - Chip
 - Resistor - Current Sense
 - Resistor - Potentiometer
 - RF Amplifier
 - RF Antenna
 - RF Attenuator
 - RF Detector
 - RF Filter
 - RF Module
 - RF Switch
 - Sensor - Current
 - Sensor - Magnetic
 - Sensor - Motion
 - Sensor - Pressure
 - Sensor - Temperature
 - Sensor - Thermocouple
 - Switch - DIP
 - Test Point
 - Thermistor - NTC
 - Video
 - Voltage Reference
 - Voltage Regulator - Linear
 - Voltage Regulator - Switchmode


##### Currently on my ToDo list:
 - STM32F series (STM32F4, STM32F3, STM32F0)
 - Si Labs Gecko series
 - Current Sensors (more of)
 - Dual Row Headers
 - Larger Terminal Blocks (5/5.08mm pitch)
 - Capacitance to Digital Converters
 - More LPC series of M0/M3/M4 (LPC4337)
 - Opto-isolators
 - RF SoC (EZR32WG, CC2640, nRF5)
 - RGB LEDS

# Contributing

Want to contribute? Great!
Join us on Discord and let the community know what you can do, we'll find something for you!

## Altium License

I have been asked several times if I have a legal Altium license - yes I do, my Altium user profile is [here (must login to view)](https://userprofile.live.altium.com/#user/EFBFF7A4-52D2-4EBA-8F30-497D6CEB8202)

License
----

You may use this library commercially in commercial designs, however you may not charge your clients for component design time if you are just going to use a part from this library. You may not charge anyone for the footprints, 3d models or schematic symbols contained in this library. You may give you clients a copy of this library, as long as you attribute the source back to this GitHub Repository. You may not claim credit for the work in this library unless you have contributed it yourself, you must give attribution where it is due.


[//]: # (These are reference links)


