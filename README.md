# ARM SWD (Single Wire Debug) Probe

Modern microcontrollers have support for the two wire debug interface SWD, which makes wiring a lot simpler.
When reverse engineering, finding these two pins is a los easier than with JTAG, where you had to wire up twice or more pins. However, finding  the two pins is still a bit of work, which gets simplified even more with this application.

This application tries to detect a valid SWD response on the wires you have picked and beeps when you have found the correct pins, showing the detected ID register and, more important, the SWD pinout. It doesn't matter which two pins you choose, just pick any two from the GPIOs on the breakout header. 

To achieve this, the application sends packets and scans the response on all pins and elaborates the pins within a few retries. Using some kind of bisect pattern reduces this number to a hand full of tries, yielding in a seemingly instant detection. 

For the user it is as simple as a continuity tester - wire up your two test needles (or accupuncture needles), connect the obvious GND pin and probe all test pads.
Now it depends on your bisect capabilities finding all pad combinations, how long it will take this time.

Video 1: https://www.youtube.com/watch?v=4vAWFcUPVeo
Video 2: https://www.youtube.com/watch?v=dmkluzQWcp4
Discussion thread: https://discord.com/channels/740930220399525928/1071712925171056690
