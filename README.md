# newfor-subtitles
Teletext subtitles on your TV. This app creates a Newfor subtitle stream from a SubRib subtitles file and connects to a Raspberry Pi teletext generator running VBIT or VBIT2.

Introduction
============
Newfor is a simple protocol for teletext subtitles. It has only four functions, Set page, load subtitle buffer, put buffer on air and finally remove subtitle. This program takes an SRT subtitle file and creates a subtitle stream from it. Because serial ports are mostly obsolete the stream uses a TCP port instead. The Raspberry Pi teletext generator VBIT-Pi-Stream or VBIT2 can accept Newfor on port 5570. The code is in the form of a Processing sketch.

How to use this code?
=====================
Install (extract from Archive downloaded) the latest version of Processing https://processing.org/download/ currently 3.3.7 (13 March 2018)

Run Processing and load newfor.pde, you will need to add a Libary called "controlP5".
In Windows version of Processing, goto the Sketch menu, choose Import Library... Add Library... serach for controlP5 (currently version 2.2.6) click Install

Then you can run it from the Processing environment. 

It should be equally happy on Windows, Linux or Mac. You can always export the application to make it into a stand-alone package.

Configuration
=============
Edit newfor.xml and set the piaddress to that of your Raspberry Pi. You can find the address as your pi should print it as the last step of the boot process. Otherwise you can use the ifconfig command. You should leave the port as 5570. The filename is not used at the moment.
<pre>
 piaddress: 192.168.1.8
 piport: 5570
 filename: Blade-Runner-Final-Cut-1982-BRRip-XviD-SLiCK.srt
</pre>
The controls are the blue buttons. RESTART is not implemented and will not work. PLAY will start running through the subtitles. After pressing play the button becomes HOLD. HOLD stops the subtitles until you press the button again. LOAD SRT File lets you choose another SubRip Text file. You can get SRT files from many places. SRT is a very simple format so you can type your own. NEXT lets you skip to the next subtitle.

The SUBTITLE STARTS time is yellow. When a subtitle is on ait it goes green. Likewise text not on air yet is yellow and it turns white when on air. 
