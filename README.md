Poker Pi
========

	Create a real time, event driven, Home Poker Tournament Manager system. Using cool new software.

Consists of 4 major components:

 * Website for a user to administer their poker tournaments 
 * Website for displaying tournament status in HTML5/CSS3 etc
 * iPad/iPhone app to allow a user to control their running poker tournament
 * API to bind all of these things together, run the tournament clocks, etc

Summary
-------

The poker tournament system will run in a web browser and show information about the running tournament.

It will show the clock, blind level, round number, players remaining, 1st place prize etc.

The player who is the designated tournament manager can control the tournament clock by:
 - using an iOS application.
 - using a website with controls/buttons on it

A raspberry pi can allow the display side of things to be done on one screen, and the iPad to be the control interface


### Website Front End

The usual register user, setup Poker Team, add players to the team, send out invitations, allow players to sign up for a poker tournament.


### iOS App 

Has 2 functions:

 1. Allows a player in a tournament to request a rebuy/addon, set their chip round and other meta data
 2. If a player is also a tournament manager they can control the tournament clock, rebuys, addons, breaks etc.


### Tournament Display
A Raspberry pi connected to a projector/TV will authenticate with the API and display information about the home users tournament.
It will appear to be controlled via a user on their iPad/iPhone starting and pausing the clock.


### Website backend
 - ZeroMQ for socket connectivity			 			http://www.zeromq.org
 - Redis for publish/subscribe to event game data.		http://redis.io
 - CakePHP API (HTML, JSON, XML etc)




Raspberry Pi
------------

Cool device, about the size of 1 deck of playing cards. 


#### Hardware Spec

 * 512MB RAM
 * 700MHz Arm11 processor
 * 16GB flash storage on memory card
 * HDMI output
 * 10/100 NIC


#### Limitations

Raspberry is the 'official' operating system for the pi but there isn't a lot of support in the open source world for precompiled binaries for the RISC architecture. 

Might run into problems trying to get some software to work/compiled. 



#### GPIO

Another of the cool things about the Pi is it's general purpose input/output (GPIO) interface which allows for real world interaction with the real world. 
It's simple to activate these pins by simply echoing 0 or 1 to the linux file system, i.e `cat 1 > /proc/gpio/1`. 

