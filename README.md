# Tenable-CTF
_##Lot's of fun Rick&Morty and Cyberpunk references##_
Team GonePhishing

Stay Away Creepy Crawlies:
Open http://167.71.246.232/robots.txt
_"A robots. txt file tells search engine crawlers which pages or files the crawler can or can't request from your site. This is used mainly to avoid overloading your site with requests; it is not a mechanism for keeping a web page out of Google."_

![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/stay_away_creepy_crawlers.png?raw=true | width=100)

Source of All Evil:
Check http://167.71.246.232/index.php source code
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/source_of_all_evil.png?raw=true)

Can't Find It:
HTTP 404 can't find page.
http://167.71.246.232/404
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/cant_find_it.png?raw=true)

Show Me What You Got:
Ran dirbuster against http://167.71.246.232/ 
Found http://167.71.246.232/images/ directory
In file: http://167.71.246.232/images/aljdi3sd.txt
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/show_me_what_you_got.png?raw=true)

Headers For Your Inspiration
Check headers in HTTP response
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/headers_for_your_inspiration.png?raw=true)

Certificate of Authenticity
Hint from name is that its something to do with SSL certificate. Change http://167.71.246.232/ to https://167.71.246.232/
Check certificate
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/certificate.png?raw=true)

Ripper Doc
http://167.71.246.232/certified_rippers.php
Hint from the Ripper Doc page.
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/ripper_doc.png?raw=true)
Changed Set-Cookie: authenticated=false to true, resent using Burp.
Can a.lso use Chrome Developer Tools with document.cookie="authenticated=true"
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/ripper_doc2.png?raw=true)
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/ripper_doc3.png?raw=true)

Follow the Rabbit Hole
http://167.71.246.232:8080/rabbit_hole.php redirects to http://167.71.246.232:8080/rabbit_hole.php?page=cE4g5bWZtYCuovEgYSO1
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/rabbit_hole1.png?raw=true)
The highlighted data can be put back into the URL loading a new page, and you follow the rabbit hole down.
Each page also has list, with an index and a hex string.
Took a little bit to figure out.
Need to go to every URL down the rabbit hole, store the index, string pair. Sort by index, then use the hex.
Quick and dirty python script that makes the requests and then script for parsing.
GITHUB LINK TO RABBIT_HOLE.PY RABBIT_HOLE_PARSE.py
Hex turns out to be an image:
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/rabbit_hole_flag.png?raw=true)

Reggie McRegex
This one was a pain. Regex was not helping me. I mostly edited this in Notepad++. 
Firstly neatened it up, then did a lot of find and replaces for patterns that couldn't be flag.. Eventually noticed a pattern.
regex = flag{[a-z_]{8,16}}
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/reggie_regex.png?raw=true)

H4ck3R_m4n exp0sed! 1 & 2 & 3
Given a pcapng, you can extract supersecure.7z, you will also find the password for the .7z
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/hackerman1.png?raw=true)
Within .7z is one flag in a JPEG, as well as a "dataz" file. From hex, from base64 with the chef and you get another JPEG.
There is an additional flag butter.jpg that can be extracted from the .7z
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/hackerman2.png?raw=true)
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/hackerman3.png?raw=true)
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/hackerman4.png?raw=true)

Tenable:
Lots of good experience with Nessus in this section.
The ultimate mutant marvel team-up
Downloaded and setup Nessus. Opened Linux scan. Exported the database, searched for flag and got the mutant flag.
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/mutant.png?raw=true)

Knowledge is knowing a tomato is a fruit
Downloaded the Nessu knowledgebase for the two machines. Bottom of one flag was there.
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/knowledge.png?raw=true)

It's twice as hard
Noticed from the export that there was a debug log called get_flag.log.
Opened it and found this:
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/twice_as_hard.png?raw=true)
Chef from hex:
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/twice_as_hard2.png?raw=true)

Pwntown :
Pwntown 1
"Beat the race in under 5 seconds"
This was obviously broken. I used Cheat Engine and speed hack.. however looks like all you had to do was walk down the left side of the map.

Pwntown 3
"Find the hidden message in the ocean"
You can see what looks like... something to the right of the map in the ocean.
Went through the unity files with Asset Studio, but no good... closer inspection shows whatever it is is made out of sprites so it won't be stored as a whole.
This one was very hard.. I have virtually zero debugging skills. So I tried Cheat Engine. Lots and lots of trial and error, managed to get my character out onto the water.
Some more cheat engine to modify the minimap in the top right so I could get a decent pic. Screen capped this:
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/pwntwn3.png?raw=true)
It's a QR code!
5 minutes to make it black and white in GIMP and its gtg.
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/qr.png?raw=true)
Scanned with QR code app.
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/pwntown3flag.png?raw=true)

Stego:
Numerological
Hint about Cistercian monks. Image is the monks shield. Used binwalk to extract second png from within.
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/shield.png?raw=true)
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/7839D.png?raw=true)
Used https://www.dcode.fr/cistercian-numbers to decode to numbers.
363736393734326536393666326634613734346136313538 decodes to this string. From hex x2 in the chef: https://git.io/JtJaX
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/monks.png?raw=true)

Weird Transmission:
There was an Alien bot in the discord playing a weird transmission.
Recorded the transmission using OBS Studio.
Lots of googling.. played around with Sonic Visualizer lots of steg checks but nothing.
In the end, found similar transmissions through googling. Used app robot32:
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/alien.png?raw=true)

A3S Turtles
Find a zip called turtles128.zip Hints are that Turtles are the way down (didnt get much help watching the seminar) and also the obvious AES128.
Theres zips nested within zips. Through john at it.. password for zip is a 0. next password was a 0.. then a 1. Ok looks like we have binary passwords, lets keep these.
Made a python script to attempt a 0 or 1 ,unzip, then continue to next turtle and store the binary. Ended up with a picture "key.png" and a 128bit string.
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/key.png?raw=true)
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/binary_aes.png?raw=true)
Lots of issues finding a decoder that worked but eventually this site came through: https://cryptii.com/pipes/aes-encryption
![alt text](https://github.com/asvardi/Tenable-CTF/blob/main/images/turtles.png?raw=true)

Others:
Completed one of the code challenges.
Attempted pretty much everything else that my teammates didn't... obviously to no success :(
