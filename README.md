# dblib
Library for AVR boards with EEPROM to access this type of memory as if it was a database. 

**dblib** makes use of the AVR-based Arduino's EEPROM memory to store records in a table. It is very simple to keep the memory footprint small. You will have to spin your own record locate and other functions like validation, but this is relatively easy to do.

## Overview
How to use in a nutshell:

* include Db.h and EEPROM.h
* declare an instance of DB, db
* define a structure for your records
* pick an address in EEPROM for the table to start
* make a little sketch that creates the table by calling db.create(address,sizeof(myRecStruct))
* in your application's sketch open the table with db.open(address)
* use the define DB_REC to cast your structure as a byte pointer when passing it as a parameter for write and read operations, this helps make the code more readable.

## Limitations
Remember that this code runs only on AVR-based boards, which typically are very limited in EEPROM memory. The general limitations to this library are:

* Tables are limited to a maximum of 255 records
* Tables are limited to the amount of EEPROM on your Arduino
* Maximum number of records: (EEPROM size / record size = max records)

## Contribute
Help maintaining this library, fork the repository and send pull requests our way.

## Credit
Originally written by Madhusudana das and stored on Google Code

Published on the Arduino Playground Wiki

Rescued by D. Cuartielles from the Google Code Archive and modified to become an official library

## License
GNU Lesser General Public License as published by the Free Software Foundation version 2.1

See [LICENSE](LICENSE) for more information
