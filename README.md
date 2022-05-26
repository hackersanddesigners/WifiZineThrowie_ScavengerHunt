<img src="./images/scavengerhunt.jpg" alt="hand holding twig with colorful wifi signal beaming out of it" width="600"/>

# Solarpunk Kids: Wifi Scavenger Hunt

## Workshop description

Is all of the Internet worldwide? Can I make my own internet? How much power does it consume? Is it bad for the environment? At Hackers & Designers we are doing experiments to find out what a sustainable Internet of the future might look like. This document is a workshop script for an intergenerational workshop where we explore these things together with 7-12 year olds and their favourite grown-ups. 

This is <strike>1-day</strike> 3-hour workshop where we will make a scavenger hunt by creating wearable wifi networks to hide digital clues about hidden treasures <strike>inside the old shipwharf/warehouse at NDSM in Amsterdam Noord</strike> in the park near Page Not Found in the Hague. 

The young participants will learn to design a scavenger hunt. The grown-up participants will learn how to build a HTML website (with some CSS and Javascript) <strike>and learn to program wearable wifi modules we will use to create the digital scavenger hunt.</strike> Together they will create small solar powered wifi hotspots with a 20-50m range. When people connect to a wifi hotspot with their phone they can find clues about where the treasures are hidden in the park!

*Note: the technical instructions in this document are biased towards MacOS operating systems, but we've included instructions for windows and linux as much as possible. Contributions specific to these operating systems are very welcome!*

The information that has a <strike>strike-through</strike> was part of the first workshop iteration, but will be left out for the 3-hour workshop (v.2).

* <strike>v1: 6-hour workshop, Saturday 7 May 2022 at NDSM Kunststad, Amsterdam</strike>
* v2: 3-hour workshop, Sunday 5 June 2022 at Page Not Found, The Hague 

**3-hour workshop outline**

* 13.00 Welcome
* 13.15 Introduction: Internet and the environment
* 13.45 Split in to Hackers & Designers
* 14.30 Group rejoins for website building and kitmaking
* 15.15 Uploading (by Loes) and downtime with tea
* 15.30 Playing the scavenger hunt in the park!
* 16.00 Round-up with icepops

*WIP! We're still in the process of editing this document*

## Table of contents with short links

* [About this project](https://github.com/hackersanddesigners/WifiZineThrowie_ScavengerHunt#about-this-project)
* [Materials and space requirements](UPDATE)
* [Workshop steps](UPDATE)
* [1. Introduction](UPDATE)
* [2. Solarpunk: What if we shrank the Internet?](UPDATE)
* [3. What are we making today?](UPDATE)
* [4. Hide the treasure & create some clues (team designers)](UDPATE)
* [5. Designing a mini webpage (team hackers)](UPDATE)
* [6. Programming the WiFi modules (workshop facilitators)](UPDATE)
* [7. Power up your module](UPDATE)
* [8. Hide your hotspots and do the scavenger hunt!](UPDATE)
* [Previous research this project builds upon](https://github.com/hackersanddesigners/WifiZineThrowie_ScavengerHunt#previous-research-this-project-builds-upon)
* [Technical details](https://github.com/hackersanddesigners/WifiZineThrowie_ScavengerHunt#technical-details)


## About this project

This workshop was developed by Hackers & Designers as part of an intergenerational collaboration on the topics of solarpunk attitudes to the Internet of the future. Together with partners Mz* Baltazar's laboratory in Vienna, and Prototype in Pittsburgh, we will develop a series of workshops to explore formats for intergenerational learning and collaboration, as well as remote collaboration structures between the different labs. This workshop script is one of the three workshops that will be developed and shared in the context of this project. 

### Hackers & Designers

Hackers & Designers is a non-profit workshop initiative organizing activities at the intersection of technology, design and art. By creating shared moments of hands-on learning H&D stimulates collaboration across disciplines, technological literacy, and different levels of expertise. [Hackers & Designers](www.hackersanddesigners.nl)

<img src="./images/hackersanddesigners.png" alt="H&D logo" width="250"/>

### Mz* Baltazar's Laboratory

Mz*Baltazar’s Lab aims at generating a culture of fearless making! An environment that fosters creativity, activism and provocative thinking! We try to build an accessible, inclusive, open, safer and radical space, from which to evolve as people and as community. Open Source Technology is at the root of our philosophy, it enables us to share and collaborate without restrictions. We need this space to experiment with things as gender, hardware or our selves. [Mz* Baltazar's Laboratory](https://www.mzbaltazarslaboratory.org/)

<img src="./images/mzbaltazar.jpg" alt="Mz* Baltazar's laboratory logo" width="250"/>


### Prototype PGH

Prototype PGH's mission is to build gender and racial equity in tech and entrepreneurship by providing affordable access to high tech tools and equipment, offering workshops that center the experiences of women and underestimated communities, and cultivating a professional support network. Prototype PGH](https://prototypepgh.com/

<img src="./images/prototypepgh.png" alt="logo of Prototype PGH" width="350"/>


### Funding

This project was kindly funded by [Fonds voor Cultuurparticipatie](https://cultuurparticipatie.nl/). 

<img src="./images/fonds-cultuurparticipatie.jpg" alt="hand holding twig with colorful wifi signal beaming out of it" width="150"/>

### Workshop background

This is an adaptation of the workshop and – amazing – documentation prepared by Wonjung Shin and Dooho Yi (Dianaband) for the Walking signal / WIFI hotspot zine workshop hosted at Hackers and Designers in 2019. See original here: [https://github.com/applecargo/WifiZineThrowie](https://github.com/applecargo/WifiZineThrowie) 

Their workshop in turn builds up on the research by Andy Reischle (AreResearch), whose research is linked to at the bottom of this page. See also [previous research this project builds upon](https://github.com/hackersanddesigners/WifiZineThrowie_ScavengerHunt#previous-research-this-project-builds-upon).

## Materials and space requirements

*Account for one kit per duo. Total cost of the components per kit is around € 25,00 ex shipping.*

- A computer per duo
- A mobile phone per duo (no dataplan needed)
- Internet connection to download libraries and look things up
- A development board with ESP32 module and 4MB flash memory, e.g. [ESP32 - CP2102](https://www.tinytronics.nl/shop/nl/development-boards/microcontroller-boards/met-wi-fi/esp32-wifi-en-bluetooth-board-cp2102)
- A short micro USB cable e.g. [this one](https://www.tinytronics.nl/shop/nl/kabels-en-connectoren/kabels-en-adapters/usb/micro-usb/micro-usb-kabel-30cm)
- A 5V charging board e.g. this [LilyGo TTGO H435 with a 18650 rechargeable battery holder](https://www.tinytronics.nl/shop/nl/power/bms-en-laders/li-ion-en-li-po/met-protectiecircuit/lilygo-ttgo-t-bat-met-18650-batterijhouder-cn3065)
- A rechargeable Li-ion battery compatible with the board, e.g. [LG 18650 Li-ion battery 3400mAh](https://www.tinytronics.nl/shop/nl/power/batterijen/18650/lg-18650-li-ion-batterij-3400mah-10a-inr18650-mj1)
- A 5.5V solar cell with JST-PH connector e.g. [Seeed Studio 5.5V Solar Panel](https://www.tinytronics.nl/shop/nl/power/zonne-energie/zonnepanelen/seeed-studio-zonnepaneel-5.5v-170ma-80x100mm-met-jst-ph-connector)
- Web page (html / css / js + media files) (provided when you download the .zip from the github explained in the steps below). 
- A puzzle (one you make or one you have!)
- Tie wraps of different sizes
- Electrical tape
- Pens and paper, cardboard, scissors, hotglue, tape

### Space

In terms of space you will need a workshop space with internet access to program the modules and create the HTML pages. 

And for the scavenger hunt, it's most fun if you have a large space to play in. The wifi modules have a range of 20-25 meters. The location for our first workshop was at an old warehouse in Amsterdam North, called NDSM Kunststad where our studio is (see pictures below).

But since it is all wireless (and solar powered), you could also play this outside! Just take a look at the weather forecast and maybe consider making waterproof cover of sorts. 

<img src="./images/kunststad1.jpg" alt="NDSM warehouse entrance" width="600"/>

<img src="./images/kunststad3.jpg" alt="hallways in NDSM warehouse" width="600"/>

<img src="./images/kunststad4.jpg" alt="outside view of NDSM warehouse" width="600"/>

<img src="./images/kunststad5.png" alt="inside square in NDSM warehouse with large colorful curtain hanging from the sealing and seating area " width="600"/>

<img src="./images/kunststad6.png" alt="one of the large empty halls inside the NDSM warehouse, lined with yellow iron columns" width="600"/>

*Images by NDSM: https://www.ndsm.nl/en/location/ndsm-loods*


## Workshop steps

## 1. Introduction

* What is your name?
* What did you have for breakfast?

<strike>Proposal: Let's discuss the following questions together briefly to find out what we already know about energy, electricity and the Internet.</strike>

Proposal: Let's discuss the following questions briefly to find out what we already know about the Internets and its environemental impact. 

**Do you use the Internet? How?**

**Where is the internet? where can you find it?**

* What devices connected to the power grid (phone/ipad/laptop > router > to server or data center)

	<img src="./images/routers.png" alt="images of a routers inside peoples homes" width="650"/> <br>*Images of routers inside peoples homes*

	<img src="./images/datacenter.png" alt="image of a datacenter" width="650"/> <br>*Image of a data center*


**How far does a website have to travel to get to your screen?**

* You want to check out a website of your friends in South-Korea [http://www.dianaband.info](http://www.dianaband.info)
* Their website lives on a computer of a host somewhere else in Seoul or around, right? Let's check: [https://hostingchecker.com](https://hostingchecker.com)
* It has to travel through all the cables under the sea and the ground to your router.

<img src="./images/underseacables2.jpg" alt="Actual undersea cable, source: BBC" width="650"/><br>*Actual undersea cable, source: BBC*

<img src="./images/underseacables.png" alt="Map of undersea cables, source: BBC" width="650"/><br>*Map of undersea cables, source: BBC*

**What makes the internet "heavy", when can you tell? How can you know?**

* bad connectivity
* slow file downloading/uploading
* images not appearing
* youtube switches to lower video quality
* Let's check out some websites. Who owns one? [https://www.websitecarbon.com](https://www.websitecarbon.com)


## 2. Solarpunk: What if we shrank the Internet? 

Being a solarpunk is about positive futures! How can we keep some of the good things of the Internet (it's fun, it's a place to share a lot of information, it's a way to connect to people), but also taking care of the environment for the future?

Some proposals we  will try out today: 

* What if an average webpage were only 1 MB (the equivalent of 1 minute of mp3 audio). To compare: if you spend 2 hours on your phone watching standard definition (SD) video, you use about 1GB of data (1GB = ~1000MB)
* What if some of the Internet wasn't worldwide but more local? 
* What if the Internet only worked when the sun shines?

<img src="./images/components.jpeg" alt="wifi module with solar panel and a battery" width="600"/>

**We made a smaller internet, let's go find it!**

* Turn off your data plan
* Look for the list of wifi networks on your phone
* Found it? Let's go out and find the network called **"solarpunk-schat"**.
* When you find it, connect to it and follow the instructions to find the first treasure.

<img src="./images/hand_schat.jpg" alt="hand holding a phone displaying list of networks with" width="600"/>

<img src="./images/interpretclues.jpg" alt="people huddled around a child with a phone, interpreting the clues displayed on the webpage" width="600"/>

<img src="./images/clue_page.jpg" alt="hands holding a phone with a webpage open providing clues to the treasure" width="600"/>

<img src="./images/treasurefound.jpg" alt="group of kids, one holding a box (the treasure)" width="600"/>

*Found it!*


<strike>
### What is energy?  

* **What is energy? Where does it come from?**

* **Energy only transforms, never disappears? What does that mean?**
	* running, getting hot
	* drinking tea, from kettle to body: electrons, the wire, heating element, the water, our body
	* electrons moving > lights, motors, buzzers go on

* **Energy game** 
	* Show a bunch of objects (see list below): Does it take or give energy? (hint: often both!) Discuss with the group how it gives and/or takes energy and why.
		* a person
		* a tree
		* a mobile phone
		* an apple
		* a lemon
		* a battery
		* a bicycle
		* a spaceship
		* a race car
		* a ball 
	
* **What alternative sources of energy do you know?**
	* Solar power
	* Dynamo
	* Lemons
	* How much electricity can you create with them? 
	* How can we store this electricity for later? (batteries! but we don't have an endless supply of batteries and they are polluting to make...)

* **Demonstrations**

	* **DIY Dynamo:** turn on an LED by twisting the axis of a 1:6 geared 12V DC motor, e.g.

		[![Lighting an LED with a DC motor](https://img.youtube.com/vi/AXfvayFPXFU/0.jpg)](https://www.youtube.com/watch?v=AXfvayFPXFU)
		<br>*Click on the image to watch on Youtube!*
	
	* Make a **lemon battery** together [instructions here](https://www.panasonic.com/global/consumer/battery/academy/lemon.html)
	
		<img src="./images/lemonbattery.jpg" alt="children measuring the output of a lemon battery with a multimeter" width="500"/>
		

### How much electricity does the Internet need?

* Do you use the Internet? When?
* Do you know how much electricity the Internet uses? How can we find out? 
	* Phones and tables need to be charged
	* Computers plugged into the wall
	* Router box plugged into the wall (have you seen yours at home?)
	* How can you find out how much power they use? (looking at markings on power plugs, battery holders)	
* What else? Where does "the Internet/tiktok/youtube videos "live"?
	* In the "cloud" (which is basically someone elses computer! What a strange name)
	* What does that look like? Search images of datacenters
	* How much energy do you think they need? (a lot!)
	* Endless videowatching and online gaming and social media using takes a lottttt of energy


</strike>


## 3. What are we making today?

This first hunt was a mini version of what we will make together. But instead of one treasure, and one mini website providing clues, each participant duo will hide a part of the treasure (a few pieces of the puzzle we created for the workshop), and make a small website providing clues about where the treasure can be found. 

<img src="./images/puzzle1.jpg" alt="jigsaw puzzle with Hackers & Designers logo" width="600"/>

But we will design the hunt ourselves! Each young participants will get some puzzle pieces to hide in the park (with Pernilla), and make clues for the others to tell them where they can find the pieces. In the meantime, the grown-ups will learn to build a small website so they can help you make a clue website for the pieces your will hide. Don't tell anyone your hiding spot? They will have to find it by searching for your hotspot on their phone, and searching the clues that you put on your website. 

* Each hacker/designer pair will hide one part of the treasure and make 1 website with clues for where to find it
* Grownups with multiple kids make 1 website together as a group, due to time constraints

When all the treasures are hidden, and all the websites are distributed around the play area, we will do the big scavenger hunt we made together and try solve the puzzle.

Before we continue: we split into groups. The young participants are the designers and the adult participants take on the hacker roles. 
 
**Designers - team B** 

Our young participants will be the designers of the scavenger hunt. With Pernilla they will explore <strike>the building</strike> the park nearby for clever hiding spots, and ways to give visual clues to find them - but not too many because we like a challenge! <strike>When that is taken care of, they will prepare lunch together, so the grown-ups can be fed around 12.30.</strike> 
 
**Hackers - team A**

In the meantime, the grown-up participants will take on the hacker roles! <strike>Depending on your interests and skillset you experiment with coding your own small website in HTML (and CSS and Javascript if you are up for it), and/or you will learn to program a small microcontroller so can act as a tiny webserver that can be used to publish the tiny websites hyperlocally (range of +/- 20 m). After all that hacking business, we will be hungry for lunch and catching up.</strike> 

After a brief tutorial, the grown-ups will play and experiment with the HTML/CSS/Javascript sample code to design their own tiny 1 MB website that will host the clues the kids will provide. 

 
<img src="./images/workshop_solar02.jpg" alt="drawing explaining roles of team A and team B and how they come together" width="600"/>


### What are these nodes? How does it work exactly? 

We will program a small wireless device with an ESP32 chip to serve a tiny (~1MB) html websites via WiFi. The module is powered by a battery, which in turn is charged by a solar cell. The Wifi module "serves" a small website anytime a smartphone tries to log on to the network it is broadcasting (like an internet hotspot). It allows you to redesign the "log-in" screen that usually pops up when you try to log on to public WiFi networks, and hijack it to publish content you want to share WiFi, but only with your neighbours and local friends within a ~25 m range. 


## 4. Hide the treasure & create some clues (team designers)

We made a jigsaw puzzle, and each young designer will get a few pieces of the puzzle to hide in the space. 

**Let's decide on the rules**

To make sure it's fun and safe for everyone, let's think about the rules we want to agree on (kids lead).

<img src="./images/rules.jpg" alt="list of rules made up by the young designers" width="600"/>

**Let's explore the space!**

<strike>NDSM is a big place with lots of fun spots!</strike> Let's explore the park nearby the workshop space! We'll walk around together to get an idea. And then you can decide which hiding spot you will choose to hide your puzzle pieces (don't show the others!)

<img src="./images/hidingspots.jpg" alt="two kids exploring the play area looking for spots to hide a treasure" width="600"/>


**Choose your hiding spot and provide clues**

Find a good hiding spot that is not clearly visible to everyone, but a little hidden from plain sight. 

Then take 2 or 3 pictures with your phone of the surrounding area to provide a clue about where the hiding spot is. 

***Tip: take one close-up picture of an interesting detail that people can recognize. And take one picture a bit further away so give some more clues about where it is. Don't make it too easy!*** 

**Back at the studio**

Think a little bit about how you want to make your clues exciting on your tiny website. Do you want to add a sound clip where you tell a story? Or some mysterious sounds? Do you want to add a drawing? What is your hiding spot called? You can design your mini website by drawing it out, and together with your grown-up start building it with code after lunch. 

Find some cardboard and make a box for your module. You can use any materials you like.

<img src="./images/decoratedbox.jpg" alt="one of the boxes decorated with various materials" width="600"/>

<strike>
**Lunch preparations**

Around 12 o'clock the designers will prepare lunch together so we can all eat! 
</strike>

## 5. Designing a mini webpage (team hackers)

Download a code editing tool to create your HTML code. We really like Brackets, because it has a feature to show you a live preview of what you are writing in the code, in a separate browser window (see below). 

- [**Brackets code editor**](https://brackets.io/) to edit your HTML page

<img src="./images/brackets_preview.png" alt="brackets code editor and preview window of the example website" width="600"/>

### Download our github repository for all the required code and HTML templates

  - Navigate to the [H&D Scavenger hunt Github Repository](https://github.com/hackersanddesigners/WifiZineThrowie_ScavengerHunt)
	
  - On the top right of the page, click 'Clone or download' -> 'Download ZIP'

  	 <img src="./images/repositoryHD.png" alt="screenshot of repository on github" width="650"/>

- **Renaming and moving the folder**
    - Decompress the .zip file by doubleclicking
    - If necessary, move the folder to some place where you would like to keep it and can find it for a while. 
    - It's good practice to change the name of the folder by deleting the part "-master" from the folder name (see images below)

	<img src="./images/listening.jpg" alt="adults and children around a table with laptops, looking at a code demonstration" width="750"/> 


### Step 1: open the example

- In the .zip file you downloaded, you can find some folders. Find the one called "code" and inside that navigate to > data > index.html

	<img src="./images/path_to_index.html.png" alt="screenshot of file path to index.html file" width="650"/> 

- If you double click it it will open a new browser window with a page that says "Hallo SolarPunk Kids"! This is what we designed as a template. 

	<img src="./images/openinbrowser.png" alt="index.html file view in a web browser" width="650"/> 

- Now you can close it. 

- Next: open the index.html file in the Brackets app you downloaded. (Right click > Open with > Brackets). 

- Now you see a text document that starts with: *<!DOCTYPE html>*. This is the HTML code, which, when opened with a browser application, displays as a colorful website with images, emojis, and cool fonts. 

- Brackets even has a function to give you a live preview. If you click on the lightning bolt on the top right, it opens a preview window with the webpage you are designing. Every time you save the code (e.g. using command + S) it will refresh the preview you you can see your changes. 

	<img src="./images/brackets_preview_bolt.png" alt="screenshot of brackets editor and preview window, with the lightning bolt marked with a circle" width="650"/> 


### Step 2: change some things

- Find line 19 in the code, where it says: "color = rebeccapurple"

- Now go ahead and instead of rebeccapurple, type "deepskyblue"

- Save the file. See how the preview changes automatically? 

	<img src="./images/rebeccapurple.png" alt="html code showing color = rebeccapurple" width="750"/> 

	<img src="./images/deepskyblue.png" alt="html code showing color = deepskyblue" width="750"/> 

	- **Tip**: if you want to try some other colors, replace the name "rebeccapurple" with a number you can look up with a color picker like this [color picker tool](https://imagecolorpicker.com/color-code/6800ff)

	<img src="./images/programmingkids.jpg" alt="young people and adults huddled around laptops, programming their html pages" width="750"/> 




### Step 3: change *more* things!

- You are probably getting bold now and want to try more! Save a copy of the index.html file so you have a copy of the original where everything still worked, just in case. 

- Now go ahead and try some other things, make small changes and save every time to see what happens. If you break it, you can always go back with command + z!

- Think of thinks like: changing the size of the emoji's to REALLY BIG! Or change the background color to something else. Or use a different font! Orrrr make some ASCII art for your web page. 

- Play around and change some things and save, change and save, change and save. You will figure out the logic of the code by doing this, and come up with ideas for your design!

- It is totally ok if you break the website, just ask for help to fix it again if you can't un-break it yourself. 

- Is it doing some thing different than what you expected? Look very carefully! Small typos can make a big difference. We're also around to help. 

**Some tools that are useful for designing your mini website**

* [Online image compression tool](https://www.iloveimg.com/compress-image) (to make your pictures smaller)
* [W3 schools tutorials](https://www.w3schools.com/html/default.asp) to look up how to write html bits and bobs
* [ASCII art generator!](https://textkool.com/en/ascii-art-generator) make art made up out of letters and numbers
* [Libre fonts by wxmen](https://www.design-research.be/by-womxn/) find a cool typeface!
* [Emoji codes](https://www.w3schools.com/charsets/ref_emoji.asp) all the emoji's you ever wanted! 
* [Color picker tool](https://imagecolorpicker.com/color-code/6800ff) to help find the code that stands for a particular color you like and want to use in the HTML.
* [Freesound archive](https://freesound.org/) to find sound clips that are free to use


<img src="./images/site1.png" alt="screenshots of a website made by participants" width="750"/> 

<img src="./images/site2.png" alt="screenshots of a website made by participants" width="750"/> 

<img src="./images/site3.png" alt="screenshots of a website made by participants" width="750"/> 





### Step 4: think of something else to try 

What else could you do? Add some interactivity? Sound? Little animated GIFs? 

Use whatever skills and knowledge you already have, or look things up on the internet (W3 schools is a nice resource, see list above). Or ask someone in the group, we all know a little bit about different things. 

**Important!**

Note that your entire website (so the index.html plus any other files like images, has to be **_around 1MB_** in total or it will fail to upload (we're not sure about the exact number) This is not a lot of space! That's why we call them tiny websites :-) If the files are too big, try compressing your images. We've listed a tool in the segment below, but Google knows many. 


## 6. Programming the WiFi modules (workshop faciltators)

For the 3-hour workshop, we will do this for you! That's because preparing your computer to program the WiFi modules takes quite some time to set up. We decided to focus on designing the websites. When you finish your page, you can give your folder with all the files to Loes and she will put them on the module. Then all you have to do is plug in the solar panel and battery, which is described in [step 4 on the bottom of this page](https://github.com/hackersanddesigners/WifiZineThrowie_ScavengerHunt#4-power-up-your-module-to-a-battery-and-solar-cell-team-a--b).

*Note for workshop facilitators: go through these steps before the workshop to make sure it all works.*

<strike>

First we need to download some tools (more to follow along the way!)

- [**Arduino Download**](https://www.arduino.cc/en/Main/Software)

- **Installing Arduino**

  - [Windows](https://www.arduino.cc/en/Guide/Windows)

  - [Mac OSX](https://www.arduino.cc/en/Guide/MacOSX)

    [![arduino-confirm](./images/arduino-confirm.png)](./images/arduino-confirm.png)

    *Click 'Open'.*

  - [Linux](https://www.arduino.cc/en/Guide/Linux)

- **Arduino IDE settings**

  - Change the compilation and upload process display mode to 'verbose mode'
 	   
 	 <img src="./images/arduino-verbose.png" alt="Arduino settings with verbose mode checked" width="600"/>


  - Check 'compile' and 'upload' in 'Show verbose output during:'

- [**Adding ESP32 boards to the Arduino IDE's board list**](https://github.com/espressif/arduino-esp32/blob/master/docs/arduino-ide/boards_manager.md)

  - Copy and paste the following into 'Additional Boards Manager URLs' and click 'Ok'.

	[![arduino-board-url](./images/arduino-board-url.png)](./images/arduino-board-url.png)

 	 ```
 	 https://dl.espressif.com/dl/package_esp32_index.json
	 ```

- **Launch the Board Manager**

 	 <img src="./images/arduino-board-manager.png" alt="screenshot showing where to path to find the board manager panel: > Tools > Board xxxx > Boards Manager " width="550"/>

- **Select the Board Manager pop-up window**
   	 
    <img src="./images/arduino-board-manager-popup.png" alt="arduino board manager popup window" width="600"/>

- **Type 'esp32' in the search box and click 'Install'**

    <img src="./images/arduino-board-manager-esp32.png" alt="board manager pop-up with esp32 typed into search box" width="600"/>


## Download our github repository for all the required code and HTML templates

Do this if you haven't done so previously. 

  - Navigate to the [H&D Scavenger hunt Github Repository](https://github.com/hackersanddesigners/WifiZineThrowie_ScavengerHunt)
	
  - On the top right of the page, click 'Clone or download' -> 'Download ZIP'

  	 <img src="./images/repositoryHD.png" alt="H&D repository on github" width="650"/>

- **Renaming and moving the folder**
    - Decompress the .zip file by doubleclicking
    - If necessary, move the folder to some place where you would like to keep it and can find it for a while. 
    - It's good practice to change the name of the folder by deleting the part "-master" from the folder name (see images below)


## Downloading and installing the ESPAsyncWebServer and AsyntTCP libraries

Next, we need some libraries. They are in the .zip file you downloaded before, but just in case they are updated in the future: here are the links to the developers' repositories. You still need to move them to the right folders on your system.  

   - Click 'Clone or download' -> 'Download ZIP' on the github page for the [ESPAsyncWebServer](https://github.com/me-no-dev/ESPAsyncWebServer).

  	 <img src="./images/arduino-00001.png" alt="Screenshot of the ESPAsyncWebServer repository on github" width="650"/>

   - Rename folder after decompression (remove the part "-master")
	   - [![arduino-00003](./images/arduino-00003.png)](./images/arduino-00003.png)
	   - [![arduino-00004](./images/arduino-00004.png)](./images/arduino-00004.png)<br>*Screenshots showing folder name, one with -master at the and and one with that part removed.*

  - Click 'Clone or download' -> 'Download ZIP' on the github page for the [AsyncTCP library](https://github.com/me-no-dev/AsyncTCP).

    [![arduino-00006](./images/arduino-00006.png)](./images/arduino-00006.png)<br>*Screenshot showing github repository of the AsyncTCP library*

    - Rename folder after decompression (remove the part "-master")

    	[![arduino-00007](./images/arduino-00007.png)](./images/arduino-00007.png)
    	[![arduino-00008](./images/arduino-00008.png)](./images/arduino-00008.png)<br>*Screenshots showing folder name, one with -master at the and and one with that part removed.*

    - Copy these 2 renamed folders to ~/Documents/Arduino/libraries. It should look like this:

    	[![arduino-00009](./images/arduino-00009.png)](./images/arduino-00009.png)<br>*Screenshot of finder window showing Arduino's libraries folder with within that the a readme.txt file and two folders, one containing AsyncTCP and the other ESPAsyncWebServer.*

## Confirming code compilation

   - Restart the Arduino IDE (the Arduino software)
   - Open 'WifiZineThrowie.ino' sketch that is inside the WiFiZineThrowie folder (in your downloads folder or on your desktop probably.
   - Select the ESP32 Dev Module board 
   
<img src="./images/arduino-wifizine-select-board.png" alt="Screenshot of Arduino menu open at > Tools > Board > ESP32 Dev Module" width="450"/>

<br><br>


## **Adjust ESP32 Dev Module board settings**

- Look up the board settings under > Tools > Most of these settings are correct by default, you just have to change QIO to DIO

      * Board: ESP32 Dev module
      * Upload Speed : 921600
      * CPU Frequency : 240MHz (WiFi BT)
      * Flash Frequency : 80MHz
      * Flash Mode : **DIO** (is QIO by default)
      * Flash Size : 4MB (32Mb)
      * Partition Scheme : Default
      * Core Debug Level : None
      * PSRAM : Disabled

   <img src="./images/arduino-wifizine-config-board.png" alt="Screenshot of board settings under > Tools in Arduino window" width="350"/>
   
   <br><br>
  
## **Compile**

* **Click on the compile button in the top left of the editor (see red arrow in pic beneath)**
      	
     <img src="./images/arduino-wifizine-popup.png" alt="arduino window with red arrow pointing to the compile button on the top left" width="350"/>

    * **If the compilation process is successful, it will say "DONE COMPILING" at the bottom**
    
    * This means Arduino confirms it can find everything it needs to upload working code 
  
    * Don't upload the code to the board yet, first we need some more stuff
	  	
		 [![arduino-wifizine-compile-done](./images/arduino-wifizine-compile-done.png)](./images/arduino-00009.png)<br>*Screenshot of Arduino window with "done compiling" message in the bottom bar of the window*

	  
* **If the compilation process ends abnormally, it will give an orange error**
  
* If necessary, troubleshoot using the error messages (if you don't get any, check that "verbose" is checked in settings of Arduino. 
    	  
	 <img src="./images/arduino-wifizine-compile-failed.png" alt="Arduino window with an orange error message" width="350"/>

## Installing a USB device driver to communicate with the ESP32 module (chip name: SiliconLabs CP2012)


### Linux 3.x.x & 4.x.x

 - Driver installation not required (included in kernel)
 	- [udev rules update required](https://docs.platformio.org/en/latest/faq.html#platformio-udev-rules)
	- [99-platformio-udev.rules](https://raw.githubusercontent.com/platformio/platformio-core/develop/scripts/99-platformio-udev.rules)

### Linux 2.6.x
[Linux 2.6.x](https://www.silabs.com/documents/login/software/Linux_2.6.x_VCP_Driver_Source.zip)
		- No information

### Windows

- [Windows 10](https://www.silabs.com/documents/public/software/CP210x_Universal_Windows_Driver.zip)
- [Windows 7/8/8.1](https://www.silabs.com/documents/public/software/CP210x_Windows_Drivers.zip)
- [Installation process](https://www.pololu.com/docs/0J7/all)


### Mac OS

  - Check if you already have this driver installed by searching your machine for a file named "SiLabsUSBDriver.kext" AND/OR "SiLabsUSBDriverYos.kext" AND/OR "SiLabsUSBDriver64.kext". On a Mac, they can be in either of these folders listed below, depending on your system. If you find nothing, proceed to install. Otherwise, uninstall using the uninstaller provided, before re-installing (drag the uninstall.sh file into a terminal window and hit enter to uninstall.

 	* /Library/Extensions/SiLabsUSBDriver.kext
	* /Library/Extensions/SiLabsUSBDriverYos.kext
	* /System/Library/Extensions/SiLabsUSBDriver64.kext
	* /System/Library/Extensions/SiLabsUSBDriver.kext
  
  - Download the driver: [Silabs USB communication chip driver download](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers)
  - Doubleclick "Install CP210x VCP Driver.app" to install it. 
  - When it gives a security message, follow the instructions to allow the install to continue


## Check if the USB driver is working

  - If you just installed the driver, restart your computer.

  - For Mac OS users: after restarting, make sure GateKeeper does not interfere with driver loading.

    - System Preferences -> Security & Privacy -> General
      
		<img src="./images/gatekeeper-check.png" alt="screenshot of mac os settings pane with the tile security & privacy highlighted" width="550"/>
      
		<img src="./images/gatekeeper-check-popup.png" alt="screenshot of the security & privacy menu at the tab general, with the window under allow apps downloaded from highlighted, this is where potential errors will show up, if any" width="550"/>

	- If there is an error message in the red box area, GateKeeper is interrupting the driver's operation. If this is the case, click 'Allow' and confirm with administrator password, **then restart your computer**.

	<img src="./images/security_and_privacy_kextload_approval.png" alt="screenshot of the settings pane - security and privacy with message System software from developer Intel Corporation Apps was blocked from loading and a button ALLOW next to it" width="550"/>
	
	
- If the problem persists, troubleshoot using the following instructions as per your operating system

### Bypassing gatekeeper on Mac OS

- [Mac OSX](https://www.silabs.com/documents/public/software/Mac_OSX_VCP_Driver.zip)
	- You need to work around a safety measure called gatekeeper which is a little different per OS operating system. Follow instructions below for your OS or google "disable gatekeeper on mac [insert your version here, e.g. monterey]" [More info here](https://support.apple.com/en-us/HT202491)

	- Mojave (10.14.x)

		- [How to disable GateKeeper](http://osxdaily.com/2016/09/27/allow-apps-from-anywhere-macos-gatekeeper/)

			```
			sudo spctl --master-disable
			```

	- High Sierra (10.13.x)

        - [How to disable GateKeeper](https://stackoverflow.com/questions/47109036/cp2102-device-is-not-listed-in-dev-on-macos-10-13)
        - [How to disable GateKeeper](https://pikeralpha.wordpress.com/2017/08/29/user-approved-kernel-extension-loading/)
        - [How to disable GateKeeper](https://www.silabs.com/community/interface/knowledge-base.entry.html/2018/03/30/usb_to_uart_bridgev-Dnef)
        - https://stackoverflow.com/questions/47109036/cp2102-device-is-not-listed-in-dev-on-macos-10-13 
        - The allow button in the settings menu might not werk, then to disable checking altogether:
			1.	Shut down your Mac
			2.	Start again while holding mac+ R during boot to enter recovery mode
			3.	Open a terminal window
			4.	type the following command and press enter

			```
			spctl kext-consent disable
			```			

			5.	Reboot
			6.	Try install driver again
	

	- Sierra (10.12.x)
        - [How to disable GateKeeper](https://www.tekrevue.com/tip/gatekeeper-macos-sierra/)

				sudo spctl --master-disable

	- El capitan (10.11.x)
		- [How to disable GateKeeper](https://medium.com/@krukmat/macos-el-capitan-enabling-usb-for-cp2102-usb-to-ttl-3b63449e02e9)
        - [csrutil enable --without kext](https://forums.developer.apple.com/thread/17452)

	- Yosemite (10.10.x)
		- [Legacy driver must be installed, instead normal one.](https://www.silabs.com/community/interface/forum.topic.html/latest_vcp_driverfo-96RK)

		<img src="./images/yosemite-cp2102.png" alt="screenshot of silabs installer window, with on the left folder called Legacy MacVCP driver" width="550"/>
        
		<img src="./images/yosemite-cp2102-legacy.png" alt="screenshot of the contents of the Legacy MacVCP driver folder, containing LegacyDriverReadme, ReleaseNotes and Silicon Labs VCP Driver" width="550"/>


### **After starting the Arduino IDE, make sure it can communicate with the ESP32 module**

- If communication is possible, you can select /dev/cu.SLAB_USBtoUART (for other than Mac OSX, this name might be different) as shown in the picture below.
    
  <img src="./images/arduino-esp32-comm.png" alt="screenshot of Arduino window with menu Tools-Port-SLAB_USBtoUART selected" width="450"/>

- If communication is not possible, SLAB_USBtoUART  will not show up (for other than Mac OSX, this name might be different.)

<img src="./images/arduino-esp32-comm-failed.png" alt="arduino-esp32-comm-failed" width="550"/>


### Upload to the Board

  - Click on the Upload button (arrow pointing right on top of the Arduino window), and then **_while_** the text '*Connecting ...*' displays in the control window at the bottom of the screen, [press and hold the' BOOT 'button on the ESP board for one second](https://randomnerdtutorials.com/solved-failed-to-connect-to-esp32-timed-out-waiting-for-packet-header/).
        
     <img src="./images/arduino-connecting.png" alt="when the output window in Arduino says CONNECTING, push the boot button on the board" width="650"/>
      
- **If the upload was successful, you will see this screen**: 
	  
	<img src="./images/arduino-wifizine-upload-done.png" alt="output window in Arduino stating Leaving...Hard resetting via RTS pin...." width="450"/>


- **If the upload was unsuccessful, you will see this error**

	[![arduino window with an orange error message](./images/arduino-wifizine-upload-failed.png)](./images/arduino-wifizine-upload-failed.png)

- [Troubleshooting tips for various problem factors here](https://randomnerdtutorials.com/esp32-troubleshooting-guide/)

- **Mac OS Monterey issue during upload**

	- If you're using Mac OS Monterey, you might get an error like this in the Arduino output window: 

		" *exec: "python": executable file not found in $PATH error on mac monterey* "

	- If that happens, open a Terminal window, and paste the code below to install the right version of Python in the right place. Then hit enter.

		```
		sed -i -e 's/=python /=python3 /g' ~/Library/Arduino15/packages/esp32/hardware/esp32/*/platform.txt
		
		```

	- Now restart the Arduino application and try uploading the code to the board again.

## Publishing your first mini webpage to the module

- The content of the small webpage we will put on the wifi modules is stored separately from the running code that takes care of publishing it. Therefore, it goes through a separate process from the usual Arduino IDE code upload process. To do this, you need to install a separate extension plug-in.

- **Download and install** [**the ESP32FS plug-in**](https://github.com/me-no-dev/arduino-esp32fs-plugin/releases)

  Create a folder called '~/Documents/Arduino/tools'

  [![Screenshot of finder window open at Arduino, showing subfolders tools](./images/arduino-esp32fs-00002.png)](./images/arduino-esp32fs-00002.png)

  Copy unpacked ESP32FS into the subfolder tools

  [![screenshot of finder window open at tools with subfolder ESP32FS inside it](./images/arduino-esp32fs-00003.png)](./images/arduino-esp32fs-00003.png)

  Be mindful with the construction of the folders. It should be installed as shown in the following figure. (Note also that the folder name is ESP32FS!)

  [![Screenshot of finder wiindow open at tools, showing filepath - ESP32FS - tool - esp32fs.jar](./images/arduino-esp32fs-00004.png)](./images/arduino-esp32fs-00004.png)

  After restarting the Arduino IDE, verify that the plug-in installation was successful. If successful, you will see a menu called 'ESP32 Sketch Data Upload' added.

  [![Screenshot of Arduino window with menu open at - Tools - ESP32 Sketch Data Upload](./images/arduino-esp32fs-00005.png)](./images/arduino-esp32fs-00005.png)

  When you click this menu option, it will move all the files in the '~/Documents/Arduino/WifiZineThrowie/data' folder to the ESP32 module's web page store.
  
### Changing the name of your wifi network

The arduino code (WifiZineThrowie.ino) specifies the name of your personal mini network by looking for a file in the data folder that ends with .ssid. In the files you downloaded you can see it is now called: "solarpunk-schat.ssid". You can change this filename to the name you like for your network (avoid symbols to be sure).  E.g. Clue1-Loes.

<img src="./images/ssid_name.png" alt="screenshot of finder window showing contents of the data folder, with the ssid file solarpunk-schat selected" width="450"/>

### Uploading your website to the module

Then, in the Arduino software, go to > Tools and select > ESP32 Sketch Data Upload 

  [![screenshot of arduino software with the WifiZineThrowie sketch open and output window saying SPIFFS uploading image...](./images/arduino-wifizine-webpage-upload.png)](./images/arduino-wifizine-webpage-upload.png)

Please execute the upload. The color of the message output during upload is displayed in white instead of red.  

While 'Connecting ...' displays, [press and hold the' BOOT 'button on the ESP board for one second](https://randomnerdtutorials.com/solved-failed-to-connect-to-esp32-timed-out-waiting-for-packet-header/).

  Screen when upload is completed successfully

  [![Screenshot of arduino window stating SPIFFS image uploaded](./images/arduino-wifizine-webpage-upload-done.png)](./images/arduino-wifizine-webpage-upload-done.png)

  Success! You can now find your private internet spot. Open the network settings on your phone, and select your network. Your website should pop up automatically, but some patience might help :) 
  
### Find your wifi network!

Look up the list of available networks on your phone with the name you provided to the .ssid file earlier. You should see your network popping up there. Try connecting to it. Your website should come up automatically with a pop-up window. 

<img src="./images/login_network.png" alt="LEFT - screenshot of android phone open at wifi menu, showing all the available networkds, with network solarpunk-schat highlighted. RIGHT - screenshot of pop-up window displaying the website contents of the html file we made" width="650"/>

### OPTIONAL - Increasing the upload capacity of the board (at your own risk)

It is possible to increase the upload capacity of the board so you can make slightly bigger websites. This is documented by Doohoyi from Dianaband, but we haven't tried it. Proceed at your own risk!

[Dianaband's workshop documentation](https://github.com/applecargo/WifiZineThrowie/blob/master/docs/index.md#increasing-the-upload-capacity-of-the-board-optional)

</strike>

## 7. Power up your module!

### Step 1: Prepare the solar panel

Enforce the connections with some electrical tape (or normal tape if you don't have any, or hotglue even). 

<img src="./images/solarpanel_tape.jpeg" alt="back of solar panel, connections enforced with electrical tape" width="650"/>

### Step 2: Insert the battery into the charging board

The flatter side is -, the less flat side is +

If you are not sure, check with a multimeter. 

A green light will turn on to indicate it is powered up. 

<img src="./images/battery_plus-minus.png" alt="close-up of the battery with LEFT showing flatter side marked with a minus sign, and RIGHT less flat side marked with a plus sign" width="650"/>

<img src="./images/battery_markings.jpeg" alt="battery holder on the back of the charging board indicating the minus and plus side" width="650"/>

### Step 3: Plug in the USB cable and power the board

Connect the solar panel to the board as indicated in the image. Plug the Wifi module to the USB port. 

If the battery is fully powered, a second light will turn on to indicate charging is done (marked CHG DONE on the PCB board). 

<img src="./images/solarpad_connections.jpeg" alt="top view of the charging board, showing where the solar pad should be connected with the JST connector" width="650"/>

### Step 4: Wrap it up nicely

Use tie-wraps to wrap everything together nice and tight. Make a little cardboard enclosure to "hide" your wifi server. 

<img src="./images/components.jpeg" width="650"/><br>*Image of all the components connected*

<img src="./images/boxes.jpg" width="650"/><br>*Examples of the boxes our test participants made :)*

## 8. Hide your hotspots and do the scavenger hunt!

When all the hotspots are programmed and powered up with a solar panel, one of the workshop facilitators will go and hide the modules in the park or space you decided to play at. 

**Make a list with the network names**

In the meantime, make a list together with all the names of your wifi modules, so everyone knows what to look for in their wifi list. Write them on a big piece of paper

<img src="./images/networkslist.jpg" width="650"/><br>*List of networks on a big piece of paper, and puzzle*

**Rules for playing**

Decide on the rules to make the game the most fun, e.g.: 

* don't tell the other players where you hid your treasure :) 
* decide on a homebase where somebody stays with the list of network names
* when you find puzzle pieces, first you have to come back to the homebase and cross off the network name from the list that you "solved"
* then you can go back in to search for another treasure
* once the are pieces of the puzzle, players can start laying the puzzle at the home base station (handy to have a table there).

**GO!**

<img src="./images/go.jpg" width="650"/><br>*go go go!*


## Previous research this project builds upon

Dianaband's workshop, and this H&D workshop builds upon the generous documentation of Andy Reischle on his blog AReResearch. Check it out! He is very funny too :) 

- [CaptiveIntraweb by AReResearch (Andy Reischle) @ 2015](https://github.com/reischle/CaptiveIntraweb)


[![Lighting an LED with a DC motor](https://img.youtube.com/vi/fQM-GHY6VJ8/0.jpg)](https://www.youtube.com/watch?v=fQM-GHY6VJ8)
<br>*Click on the image to watch on Youtube!*

<img src="./images/areresearch/img4.png" width="650"/><br>*Diagram of the protocol we are using with our set-up, made by Andy Reischle*

## Technical details 

Below is a diagram and list of technologies ("stack") that makes up this application. This information was compiled by Dianaband for the original workshop. 

- Intangible components
  - [ESP-IDF Development Environment](https://github.com/espressif/esp-idf/tree/master/components)
  - [ESP32 Arduino Compatibility Package](https://github.com/espressif/arduino-esp32)
  - [SPIFFS file system](https://github.com/espressif/arduino-esp32/tree/master/libraries/SPIFFS)
  - [ESP web server library](https://github.com/me-no-dev/ESPAsyncWebServer)
  - [A domain name server (captive portal)](https://github.com/espressif/arduino-esp32/tree/master/libraries/DNSServer)
  - Webpage (the one you wrote in HTML)

<img src="./images/Wi-Fi-zine-stacks.png" width="750"/><br>*Diagram of the technology stack used in the project*

  - [More information](http://esp32.net/)
  - [The Wi-Fi stack is not open source](https://github.com/espressif/esp32-wifi-lib/issues/2)


