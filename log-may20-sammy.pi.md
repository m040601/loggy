RADIO
====

ft8 [WSJT (amateur radio software) - Wikipedia](https://en.wikipedia.org/wiki/WSJT_(amateur_radio_software)#FT8)
---

WSJT (Weak Signal communications, by K1JT) beziehungsweise WSJT-X als
deren aktuelle Version, ist eine Gruppe von Übertragungsprotokollen und
eine freie Amateurfunk-Software zur Kommunikation mithilfe von schwachen
Signalen. .

FT8 ist eine im Amateurfunk benutzte digitale Betriebsart zur drahtlosen
Kommunikation. Sie wird von Funkamateuren insbesondere auf Kurzwellen
genutzt. .

WSJT is a computer program used for weak-signal radio communication
between amateur radio operators. The program was initially written by
Joe Taylor, K1JT, but is now open source and is developed by a small
team. The digital signal processing techniques in WSJT make it
substantially easier for amateur radio operators to employ esoteric
propagation modes, such as high speed meteor scatter and moonbounce.[2]
.



dtmc raspberry pi radio remote automation
-----

[Raspberry Pi Ham Radio Remote Reviewed | Hackaday](https://hackaday.com/2019/10/07/raspberry-pi-ham-radio-remote-reviewed/)
One problem with ham radio these days is that most hams live where you
can’t put a big old antenna up due to city laws and homeowner covenants.
If you’re just working local stations on VHF or UHF, that might not be a
big problem. But for HF usage, using a low profile antenna is a big
deal. However, most modern radios can operate remotely. Well-known ham
radio company MFJ now has the RigPi Station Server and [Ham Radio DX]
has an early version and did a review..

https://hackaday.com/2019/03/15/the-50-ham-entry-level-transceivers-for-technicians/

[Raspberry Pi Takes Control Of Ham Radio | Hackaday](https://hackaday.com/2020/06/24/raspberry-pi-takes-control-of-ham-radio/)
https://github.com/notpike/Hambone
Hambone is a Ham Radio Bot built for the Raspberry Pi. It acts as
computer interface for your radio by listening for DTMF commands and can
activate the radio's PTT via the RPI's GPIO to play audio. Think of this
as an IRC bot but with a radio!.

GPS
====

my own base station gps rtk for precision agriculture
----
Skytraq PX1122R Tiny Multi-Band RTK GNSS Module Offers Centimeter Accuracy (https://www.cnx-software.com/2020/05/08/skytraq-px1122r-tiny-multi-band-rtk-gnss-module-offers-centimeter-accuracy/)

> Centimeter-level precision can be used for agriculture, machine
> control guidance (UAV), survey and GIS data collection, structure, and
> deformation monitoring. RTK applications require a base and a rover.
> The base can either be a third-party RTK base station service, or a
> PX1122R module configured accordingly..
esp
===

[Three-Dollar Router Rebooter Has One Job | Hackaday](https://hackaday.com/2020/05/06/three-dollar-router-rebooter-has-one-job/)



ota over the air updates
---

[OTA ESP32 GUI Makes Updates Simple | Hackaday](https://hackaday.com/2020/06/23/ota-esp32-gui-makes-updates-simple/)
https://hackaday.com/2020/06/23/ota-esp32-gui-makes-updates-simple/
[krdarrah/ESP32_GUI_Programmer: Processing Based GUI for Programming ESP32 modules based on espota.py](https://github.com/krdarrah/ESP32_GUI_Programmer)


bluetooth
====

metabest - digital contact tracing - hardware token - bluetrace opentrace - singapore swiss covide et al
----











https://github.com/opentrace-community
https://bluetrace.io/
[Digital contact tracing - Wikipedia](https://en.wikipedia.org/wiki/Digital_contact_tracing)
[Contact tracing - Wikipedia](https://en.wikipedia.org/wiki/Contact_tracing)

Technology
Mobile phones
Main article: COVID-19 apps

On 10 April 2020, Apple and Google, who account for most of the world's
mobile operating systems, announced Coronavirus disease 2019 tracking
technology for iOS and Android.[7][8] Relying on Bluetooth Low Energy
(BLE) wireless radio signals for contact tracing,[9] the new tools would
warn people about others they'd been in contact with who are infected by
SARS-CoV-2.

As of 10 April, corresponding coronavirus apps were expected to be released in May and enhanced later in 2020.[8]
Protocols
Various protocols, such as Pan-European Privacy-Preserving Proximity
Tracing (PEPP-PT),[10] Whisper Tracing Protocol[11], Decentralized
Privacy-Preserving Proximity Tracing (DP-PPT/DP-3T),[12][13] TCN
Protocol, Contact Event Numbers (CEN), Privacy Sensitive Protocols And
Mechanisms for Mobile Contact Tracing (PACT)[14] and others, are being
discussed to preserve user privacy. .


[BlueTrace - Wikipedia](https://en.wikipedia.org/wiki/BlueTrace)
BlueTrace is an open-source application protocol that facilitates
digital contact tracing of users to stem the spread of the COVID-19
pandemic.[2] Initially developed by the Singaporean Government,
BlueTrace powers the contact tracing for the TraceTogether app.[3]
Australia has already adopted the protocol [4][5], and many other
countries such as New Zealand are considering BlueTrace for
adoption.[6][7] A core principle of the protocol is the preservation of
privacy and health authority co-operation.[8] .

https://en.wikipedia.org/wiki/TraceTogether
https://en.wikipedia.org/wiki/Pan-European_Privacy-Preserving_Proximity_Tracing
https://en.wikipedia.org/wiki/Exposure_Notification
https://en.wikipedia.org/wiki/TCN_Protocol
https://en.wikipedia.org/wiki/Decentralized_Privacy-Preserving_Proximity_Tracing

### bunny simmel nordic nrf52833

The Simmel team is funded through the NGI0 PET Fund, a fund established
by NLnet with financial support from the European Commission's Next
Generation Internet programme, under the aegis of DG Communications
Networks, Content and Technology under grant agreement No 825310..


Simmel is being developed on a very short timeframe. We have two paths being explored in parallel.

    The BLE variant facilitates contact tracing via BLE.
    The NUS variant facilitates contact tracing via near ultrasound (NUS).

[Simmel | Simmel Project](https://simmel.betrusted.io/)
Simmel is a platform that enables COVID-19 contact tracing while
preserving user privacy. It is a wearable hardware beacon and scanner
which can broadcast and record randomized user IDs. Contacts are stored
within the wearable device, so you retain full control of your trace
history until you choose to share it..

https://github.com/simmel-project/frontpage
https://www.bunniestudios.com/blog/?p=5820
https://simmel.betrusted.io/

### singapore hw token
[Teardown Of The Singaporean COVID-19 TraceTogether Token | Hackaday](https://hackaday.com/2020/06/25/teardown-of-the-singaporean-covid-19-tracetogether-token/)
Recently, [Sean] along with [Andrew “bunnie” Huang] and a few others
were asked by GovTech Singapore to review their TraceTogether hardware
token proposal. At its core it’s similar to the Simmel contact tracing
solution – on which both are also working – with contacts stored locally
in the device, Bluetooth communication, and a runtime of a few months or
longer on the non-rechargeable batteries..


[Trace Together Token: Teardown and Design Overview](https://xobs.io/trace-together-token-teardown/)
 This token removes the need to carry a phone at all times, and is
 designed to help both those who do not have a smart device capable of
 running TraceTogether well, including those using older Android
 devices, non-smartphones, and iOS users. .


There is no battery charger – it's designed to run for several months on a single battery.
    The entire system must be extremely low power

The last point means it is unlikely that they hid a GPS tracker, WiFi
radio, or cellular modem in this device. The battery is a small coin
cell, which would only last a few hours if it were receiving GPS or
communicating via WiFi.


IR
====

tv be gone - turn off
----
[Homemade Arduino TV-B-Gone : 4 Steps (with Pictures) - Instructables](https://www.instructables.com/id/Homemade-Arduino-TV-B-Gone/)


CNC
====



[OpenPnP – Open Source SMT Pick and Place](http://openpnp.org/)
----
[How To Retrofit A Pick And Place Machine For OpenPnP, In Detail | Hackaday](https://hackaday.com/2020/06/24/how-to-retrofit-a-pick-and-place-machine-for-openpnp-in-detail/)
[LitePlacer pick and place introduction - YouTube](https://www.youtube.com/watch?v=T_v2VJKNZQ0)
https://github.com/openpnp/openpnp
OpenPnP is an Open Source SMT pick and place system that includes ready
to run software, and hardware designs that you can build and modify. You
can also use OpenPnP software to run a pick and place machine of your
own design, or with existing commercial machines, giving them abilities
they never had with their OEM software..
duino
====



arduino ota updates with nrf24
-----
https://github.com/nschurando/optiboot-nrf24l01

https://www.youtube.com/watch?v=8xJqVeZkEw8
https://www.2bitornot2bit.com/blog/arduino-bootloader-with-ota-over-the-air-support-over-nrf24l01
https://hackaday.com/2018/01/18/over-the-air-updates-for-your-arduino/
ROLLING
====
