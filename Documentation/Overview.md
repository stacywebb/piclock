# Overview of the PiClock

## Introduction

The PiClock is a clock, weather forcast, and radar map display
based on the Raspberry Pi and a display monitor. The display monitor is
assumed to be an HDMI monitor, but it will probably (possibly) work with
the composite output as well, but this is not a design goal.  The main
program (Clock/PyQtPiClock.py) will also run on Windows, Mac, and Linux,
as long as python 2.7+ and PyQt4 is installed.

The Weather data comes from Weather Underground using their API 
( http://www.wunderground.com/weather/api/ ).   The maps are from
Google Maps API.   **You must get an API Key from weather
underground in order to make this work.**  It is free for low
usage such as this application.

The PiClock can be customized with several supported additional things:
  * RGB LED strips (NeoPixel) to create an ambilight effect
  * gpio buttons for changing the view
  * IR Remote Control for changing the view
  * Streaming the NOAA weather radio stream for your area

The power usage I've measured is about 35watts with a 19" HDMI Monitor, 27 LEDs and the Pi.
The LEDs contributed 3 or so watts, and I think the Pi is about 2-3 Watts normally.

This is the basic PiClock, with some options added.
![PiClock Picture](https://raw.githubusercontent.com/stacywebb/piclock/master/Pictures/piclock_1.jpg)



## List of materials

So what do you need to build a PiClock?

  * A Raspberry Pi (revision 2) Model B, or B+, Pi 2 Model B or Pi 3 Model B
  * A Display Monitor & Cable
  * Power Supply (or if you're ambitious tap your display power supply,
    you'll probably need a switching down regulator to 5v)  Remember
    the Pi likes something that can source up to 2A.
  * A USB Keyboard and Mouse for setup (if you want something small
    and semi-permanent, I've had good luck with this: 
    https://www.google.com/search?q=iPazzPort+2.4G+Mini+Wireless+Keyboard 
    I like the one with the mousepad on the side)
  * USB Wifi or Internet Connection

Optional things

  * One or more DS18B20s for showing the inside temperature ( https://www.google.com/#q=ds18b20 )
  * A string of WS2818 based RGB LEDs for the AmbiLight effect.  At 40ma per LED, and 30 or so
    LEDs you're quickly up to needing an extra 1.2A from the power supply.  Size it appropriately.
    One option is https://learn.adafruit.com/adafruit-neopixel-uberguide/overview)
  * A TSOP4838 IR Receiver to flip the page display of the PiClock (https://www.google.com/search?q=tsop4838)
  * An IR Remote control ( I use this little guy: https://www.google.com/search?q=Mini+Universal+Infrared+IR+TV+Set+Remote+Control+Keychain )
  * Button or buttons connected to some GPIO pins (and a ground pin) for flipping pages like the IR remote

## What else?

The Hardware guide ( https://github.com/stacywebb/piclock/blob/master/Documentation/Hardware.md )
gives more details about how to wire/connect the various extras.

The Install guide ( https://github.com/stacywebb/piclock/blob/master/Documentation/Install.md )
steps through all the things that you need to do to a stock Raspbian image to make the PiClock work.

## Not a Pi Person?

If you want to use the piclock on your desktop (not your Pi), I've created instructinos for that
https://github.com/stacywebb/piclock/blob/master/Documentation/Install-Clock-Only.md


