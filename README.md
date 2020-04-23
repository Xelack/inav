![INAV](http://static.rcgroups.net/forums/attachments/6/1/0/3/7/6/a9088858-102-inav.png)
![Travis CI status](https://travis-ci.com/Xelack/inav-F3-Ext.svg?branch=master)

# This project is fork from INAV V2.1.0 - navigation capable flight controller 

# The little story of a fork Y ^^
I'm started this fork based first on my personal need to build a DIY Drone started in 2017 but never endded due to very streng life for greates things... two beautiful childrens lol
So I return on this topic on 2020, in "covid" context, confined with a fee time free.
Ready to go to lastest INAV version (V2.4), quick review on realease note and let's go to flash my old (but not too bad) F3 FC board...

First misaventure, true in 2017 but always true in 2020, is that my FC is always not officially supported. 
In 2017, after some mails, Holybro send me a steps to flash my RACE32 with SPRACINGF3 witch is the more compatible firmware with my FC in Cleanfligth (the base of Inav).

Ok, my FC run in INAV 2.4 SPRACINGF3, I send my diff in the CLI and look results ...some (parsing) errors. 

Remarks, I builded this quadcopter not in the goal to do flying score in time or in speed, but in goal to learn about this new great "technology" and for my personal curriosity. In that objective all component are inexpensive but with "decent" reliability for flying above the fields.

My PWM RX it's not longer supported for performance issue (if I not wrong) due to new features added and to maintain GPS correct working (good raisons). 
So I change firmware for last version with PWM RX support (V2.1.0).
I retry, ..KO! the map command cannot support more than 4 characters in V2.1 but with SPRACINGF3 firmware I need to use AE34TR12 mapping (bad things but worked in the V1.7) because the pcb design is little bit different for the plugs.

At this point, three possible options 

1 ) Downgrade to Inav V1.7, not so bad but too easy solution for my "sick mind", I thinks lol

2 ) Buy PWM to PPM converter : in this pendemie context I not found any sellers with decent price, and I'm not very happy to put more cash in this "low cost" quad.

3 ) Try to add my FC board on version V2.1 witch she have the PARALLELE PWM RX support (so less efforts for myself).

# Fork for what?
For my needs? No! An Idea? YES but to share it with tech' enthousiast peoples like me!

In these last years, I'm worked with friends on some domotic's projects based on Arduino and the ESP32 modules.
I thinks that module (ESP32 or ESP32 based) extend the possibilities of FC board with few impact on fligth caracteristics.
But to have power supply consumtion in raisonable limite, the F3 MCU it's not bad choice due to her performance/consumition ratio. 

Other important objectif on this solution is to give more reliability and robustness of the FC software to do the crititicals tasks and let's others not essential tasks for the extension module.  

Now imagine these new features for the futur...

I hope to found quickly collaborators to work on this projet, I'll enable the dev sharing when my backlog is ready and all dev tools configured.

Don't hesited to send me your questions or remarks :)

## Features inherited from INAV

* Outstanding navigation performance out of the box
* Position Hold, Altitude Hold, Return To Home and Missions
* Excellent support for fixed wing UAVs: airplanes, flying wings 
* Pitot tube support
* Rangefinder support (sonar and laser)
* Oneshot and Multishot ESC support.
* Blackbox flight recorder logging (to onboard flash or external SD card).
* Lux's new PID (uses float values internally, resistant to looptime variation).
* Simultaneous Bluetooth configuration and OSD.
* LTM Telemetry.
* Smartport Telemetry.
* RSSI via ADC - Uses ADC to read PWM RSSI signals, tested with FrSky D4R-II and X8R.
* OLED Displays - Display information on: Battery voltage, profile, rate profile, version, sensors, RC, etc.
* In-flight manual PID tuning and rate adjustment.
* Rate profiles and in-flight selection of them.
* Multiple simultaneous telemetry providers.
* Configurable serial ports for Serial RX, Telemetry, MSP, GPS - Use most devices on any port, softserial too.
* Multi-color RGB LED Strip support (each LED can be a different color using variable length WS2811 Addressable RGB strips - use for Orientation Indicators, Low Battery Warning, Flight Mode Status, etc)
* PIDs from CF/BF can be used in INAV, no need to retune for INAV
* And many more!

For a list of features, changes and some discussion please review consult the releases [page](https://github.com/Xelack/inav-F3-Ext/releases) and the documentation.

## Tools

### INAV Configurator
ONLY USE THE V2.1.x FOR NOW !!!! Others version are not supported. 

Official tool for INAV can be downloaded [here](https://github.com/iNavFlight/inav-configurator/releases/tag/2.1.4). 
It can be run on Windows, MacOS and Linux machines and standalone application.  

(Note: on linux do not miss to add execution autorisation on "configurator" file)

### INAV Blackbox Explorer

Tool for Blackbox logs analysis is available [here](https://github.com/iNavFlight/blackbox-log-viewer/releases)

### Telemetry screen for OpenTX

Users of FrSky Taranis X9 and Q X7 can use INAV Lua Telemetry screen created by @teckel12 . Software and installation instruction are available here: [https://github.com/iNavFlight/LuaTelemetry](https://github.com/iNavFlight/LuaTelemetry)

## Installation

See: https://github.com/Xelack/inav-F3-Ext/blob/master/docs/Introduction.md

## Documentation, support and learning resources

* [Official documentation](https://github.com/Xelack/inav-F3-Ext/tree/master/docs)
* [Official Wiki](https://github.com/Xelack/inav-F3-Ext/wiki)
* [INAV Official on Gitter](https://gitter.im/inav-F3-Ext/)
* [Video series by Painless360](https://www.youtube.com/playlist?list=PLYsWjANuAm4qdXEGFSeUhOZ10-H8YTSnH)
* [Video series by Paweł Spychalski](https://www.youtube.com/playlist?list=PLOUQ8o2_nCLloACrA6f1_daCjhqY2x0fB)

## Contributing

Contributions are welcome and encouraged.  You can contribute in many ways:

* Documentation updates and corrections.
* How-To guides - received help?  help others!
* Bug fixes.
* New features.
* Telling us your ideas and suggestions.
* Buying your hardware from this [link](https://inavflight.com/shop/u/bg/)

A good place to start is Gitter Room. Drop in, say hi.

Github issue tracker is a good place to search for existing issues or report a new bug/feature request:

https://github.com/Xelack/inav-F3-Ext/inav/issues

Before creating new issues please check to see if there is an existing one, search first otherwise you waste peoples time when they could be coding instead!

## Developers

Please refer to the development section in the [docs/development](https://github.com/Xelack/inav-F3-Ext/tree/master/docs/development) folder.


## INAV Releases
https://github.com/Xelack/inav-F3-Ext/releases

# Special Thanks !

Thanks a lot "INAV" for the very good job realise and more for sharing it with the world !!!!!!!

[Please excuse my bad english but I work on it!]
