![hotspot-zine-ssid](./images/scavengerhunt.jpg)

# Solarpunk Kids: Wifi Scavenger Hunt 

This is an adaptation of the workshop and – amazing – documentation prepared by Wonjung Shin and Dooho Yi (Dianaband) for the Walking signal / WIFI hotspot zine workshop hosted at Hackers and Designers in 2019. See original here: [https://github.com/applecargo/WifiZineThrowie](https://github.com/applecargo/WifiZineThrowie) 

**WIP! Still needs to be edited/adapted for solarpunk workshop.**

**To Do**: 

 * link download Sublime text or other code/html editor
 * add own intro and activities (so it becomes workshop script)
 * image captions/alt text


## Materials and preparations

- A computer
- A Development board with ESP32 module
- A Micro USB cable for communication (Android data cable)
- Battery, battery pack or DC adapter
- Web page (html / css / js + media files)
- (Optionally) a sensor or actuator (such as a speaker)

## Preparing Hot-spot zine platform

- [**Arduino Download**](https://www.arduino.cc/en/Main/Software)

- **Installing Arduino**

  - [Windows](https://www.arduino.cc/en/Guide/Windows)

  - [Mac OSX](https://www.arduino.cc/en/Guide/MacOSX)

    [![arduino-confirm](./images/arduino-confirm.png)](./images/arduino-confirm.png)

    *Click 'Open'.*

  - [Linux](https://www.arduino.cc/en/Guide/Linux)

- **Arduino IDE launch screen**

	[![arduino-screen](./images/arduino-screen.png)](./images/arduino-screen.png)

- **Arduino IDE settings**

  - Change the compilation and upload process display mode to 'verbose mode'

 	   [![arduino-verbose](./images/arduino-verbose.png)](./images/arduino-verbose.png)

  - Check 'compile' and 'upload' in 'Show verbose output during:'

- [**Adding ESP32 boards to the Arduino IDE's board list**](https://github.com/espressif/arduino-esp32/blob/master/docs/arduino-ide/boards_manager.md)

  - Copy and paste the following into 'Additional Boards Manager URLs' and click 'Ok'.

	[![arduino-board-url](./images/arduino-board-url.png)](./images/arduino-board-url.png)

 	 ```
 	 https://dl.espressif.com/dl/package_esp32_index.json
	 ```

- **Launch the Board Manager**

	[![arduino-board-manager](./images/arduino-board-manager.png)](./images/arduino-board-manager.png)

- **Select the Board Manager pop-up window**

   	 [![arduino-board-manager-popup](./images/arduino-board-manager-popup.png)](./images/arduino-board-manager-popup.png)

- **Type 'esp32' in the search box and click 'Install'**

    [![arduino-board-manager-esp32](./images/arduino-board-manager-esp32.png)](./images/arduino-board-manager-esp32.png)

## Download Dianaband's WifiZineThrowie code and required libraries

  - Navigate to the [WifiZineThrowie Github Repository](https://github.com/applecargo/WifiZineThrowie/) download and installation
	
  - Click 'Clone or download' -> 'Download ZIP'

   	[![arduino-00010](./images/arduino-00010.png)](./images/arduino-00010.png)

- **Renaming and moving the folder**
    - Decompress the .zipfile by doubleclicking
    - Then change the name by deleting the part "-master" from the folder name (see images below)

    	[![arduino-00011](./images/arduino-00011.png)](./images/arduino-00011.png)
    	[![arduino-00012](./images/arduino-00012.png)](./images/arduino-00012.png)

    - Copy that folder to ~/Documents/Arduino (the '~' sign means your home folder)

    	[![arduino-00013](./images/arduino-00013.png)](./images/arduino-00013.png)

## Downloading and installing the ESPAsyncWebServer and AsyntTCP libraries

   - Click 'Clone or download' -> 'Download ZIP' on the github page for the [ESPAsyncWebServer](https://github.com/me-no-dev/ESPAsyncWebServer).

   [![arduino-00001](./images/arduino-00001.png)](./images/arduino-00001.png)

   - Rename folder after decompression (remove the part "-master")

   	 	[![arduino-00003](./images/arduino-00003.png)](./images/arduino-00003.png)
    	[![arduino-00004](./images/arduino-00004.png)](./images/arduino-00004.png)

  - Click 'Clone or download' -> 'Download ZIP' on the github page for the [AsyncTCP library](https://github.com/me-no-dev/AsyncTCP).

    [![arduino-00006](./images/arduino-00006.png)](./images/arduino-00006.png)

    - Rename folder after decompression (remove the part "-master")

    	[![arduino-00007](./images/arduino-00007.png)](./images/arduino-00007.png)
    	[![arduino-00008](./images/arduino-00008.png)](./images/arduino-00008.png)

    - Copy these 2 renamed folders to ~/Documents/Arduino/libraries. It should look like this:

    	[![arduino-00009](./images/arduino-00009.png)](./images/arduino-00009.png)

## Confirming code compilation

   - Restart the Arduino IDE (the Arduino software)

    - Open 'WifiZineThrowie.ino' sketch that is inside the WiFiZineThrowie folder (in your downloads folder or on your desktop probably.  t(from > File > Sketchbook)

    - Select the ESP32 Dev Module board

      [![arduino-wifizine-select-board](./images/arduino-wifizine-select-board.png)](./images/arduino-wifizine-select-board.png)

    - Adjust ESP32 Dev Module board settings

      [![arduino-wifizine-config-board](./images/arduino-wifizine-config-board.png)](./images/arduino-wifizine-config-board.png)


	- **Most of these settings are correct by default, you just have to change QIO to DIO**
		
	      - Upload Speed : 921600
	      - CPU Frequency : 240MHz (WiFi BT)
	      - Flash Frequency : 80MHz
	      - Flash Mode : **DIO** (is QIO by default)
	      - Flash Size : 4MB (32Mb)
	      - Partition Scheme : Default
	      - Core Debug Level : None
	      - PSRAM : Disabled

    - **Click on the compile button in the top left of the editor (see red arrow in pic beneath)**

      	[![arduino-wifizine-popup](./images/arduino-wifizine-popup.png)](./images/arduino-wifizine-popup.png)

    - **If the compilation process is successful, it will say "DONE COMPILING" at the bottom**
    
    - This means Arduino confirms it can find everything it needs to upload working code 
    - Don't upload the code to the board yet, first we need some more stuff

	  	[![arduino-wifizine-compile-done](./images/arduino-wifizine-compile-done.png)](./images/arduino-wifizine-compile-done.png)

    - **If the compilation process ends abnormally, it will give an orange error**
  
    	- If necessary, troubleshoot using the error messages (if you don't get any, check that "verbose" is checked in settings of Arduino. 

    	  [![arduino-wifizine-compile-failed](./images/arduino-wifizine-compile-failed.png)](./images/arduino-wifizine-compile-failed.png)

## Installing a USB device driver to communicate with the ESP32 module (chip name: SiliconLabs CP2012)

  - [USB communication chip driver download](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers)

    - [Windows 10](https://www.silabs.com/documents/public/software/CP210x_Universal_Windows_Driver.zip)
    - [Windows 7/8/8.1](https://www.silabs.com/documents/public/software/CP210x_Windows_Drivers.zip)

      - [Installation process](https://www.pololu.com/docs/0J7/all)

    - [Mac OSX](https://www.silabs.com/documents/public/software/Mac_OSX_VCP_Driver.zip)

      - [GateKeeper is a bastard!](https://support.apple.com/en-us/HT202491)

      - Yosemite (10.10.x)

        - [Legacy driver must be installed, instead normal one.](https://www.silabs.com/community/interface/forum.topic.html/latest_vcp_driverfo-96RK)

        [![yosemite-cp2102](./images/yosemite-cp2102.png)](./images/yosemite-cp2102.png)
        [![yosemite-cp2102-legacy](./images/yosemite-cp2102-legacy.png)](./images/yosemite-cp2102-legacy.png)

      - El capitan (10.11.x)

        - [How to disable GateKeeper](https://medium.com/@krukmat/macos-el-capitan-enabling-usb-for-cp2102-usb-to-ttl-3b63449e02e9)
        - [csrutil enable --without kext](https://forums.developer.apple.com/thread/17452)

      - Sierra (10.12.x)

        - [How to disable GateKeeper](https://www.tekrevue.com/tip/gatekeeper-macos-sierra/)
        - sudo spctl --master-disable

      - High Sierra (10.13.x)

        - [How to disable GateKeeper](https://stackoverflow.com/questions/47109036/cp2102-device-is-not-listed-in-dev-on-macos-10-13)
        - [How to disable GateKeeper](https://pikeralpha.wordpress.com/2017/08/29/user-approved-kernel-extension-loading/)
        - [How to disable GateKeeper](https://www.silabs.com/community/interface/knowledge-base.entry.html/2018/03/30/usb_to_uart_bridgev-Dnef)
        - spctl kext-consent disable

      - Mojave (10.14.x)

        - [How to disable GateKeeper](http://osxdaily.com/2016/09/27/allow-apps-from-anywhere-macos-gatekeeper/)
        - sudo spctl --master-disable

    - Linux 3.x.x & 4.x.x

      - Driver installation not required (included in kernel)
      - [udev rules update required](https://docs.platformio.org/en/latest/faq.html#platformio-udev-rules)
      - [99-platformio-udev.rules](https://raw.githubusercontent.com/platformio/platformio-core/develop/scripts/99-platformio-udev.rules)

    - [Linux 2.6.x](https://www.silabs.com/documents/login/software/Linux_2.6.x_VCP_Driver_Source.zip)

      - No information

- Check if the USB driver is working

  - If you just installed the driver, restart your computer.

  - After restarting, make sure GateKeeper does not interfere with driver loading.

    - System Preferences -> Security & Privacy -> General

      [![gatekeeper-check](./images/gatekeeper-check.png)](./images/gatekeeper-check.png)
      [![gatekeeper-check-popup](./images/gatekeeper-check-popup.png)](./images/gatekeeper-check-popup.png)

      If there is an error message in the red box area, GateKeeper is interrupting the driver's operation.

      [![security_and_privacy_kextload_approval](./images/security_and_privacy_kextload_approval.png)](./images/security_and_privacy_kextload_approval.png)

      If you are in a similar state as above, click 'Allow' and confirm with administrator password, then restart your computer.

  - After starting the Arduino IDE, make sure it can communicate with the ESP32 module

    [![arduino-esp32-comm](./images/arduino-esp32-comm.png)](./images/arduino-esp32-comm.png)

    If communication is possible, you can select /dev/cu.SLAB_USBtoUART (for other than Mac OSX, this name might be different.) as above.

    [![arduino-esp32-comm-failed](./images/arduino-esp32-comm-failed.png)](./images/arduino-esp32-comm-failed.png)

    If communication is not possible, /dev/cu.SLAB_USBtoUART (for other than Mac OSX, this name might be different.) does not exist as above.

- Set the name of the Wi-Fi network i.e. SSID of the Hot-spot zine, and modify the code.

  [![arduino-wifizine-ssid-change](./images/arduino-wifizine-ssid-change.png)](./images/arduino-wifizine-ssid-change.png)

  - Since it may not work due to the number of characters or spacing, we try firstly with simple and short English names that does not include a space character.
  - Hangul(or any other non-English characters) may be used. (later, trial and error)

- Upload to the Board

  - Click on the Upload button (red arrow), while 'Connecting ...' displays, [press and hold the' BOOT 'button on the ESP board for one second](https://randomnerdtutorials.com/solved-failed-to-connect-to-esp32-timed-out-waiting-for-packet-header/).

    [![arduino-wifizine-upload](./images/arduino-wifizine-upload.png)](./images/arduino-wifizine-upload.png)

    Upload success screen

    [![arduino-wifizine-upload-done](./images/arduino-wifizine-upload-done.png)](./images/arduino-wifizine-upload-done.png)

    Upload error screen

    [![arduino-wifizine-upload-failed](./images/arduino-wifizine-upload-failed.png)](./images/arduino-wifizine-upload-failed.png)

- [Various problem factors](https://randomnerdtutorials.com/esp32-troubleshooting-guide/)

### Increasing the upload capacity of the board (optional)

- The flash memory capacity of the provided ESP32 module is 4MB, but not all of this is usable for Zine content. The reason for this is that many other things also need their spaces: the codes that runs the hotspot-zine, the codes that runs background to support the chip function and the data used to represent the structure of the file system (such as folder structure and file distinction), that is, the implementation overhead of SPIFFS. So we cannot claim whole memory space of 4MB.

- The flash memory of the ESP32 module must be partitioned first to be used partly with different purposes.

- During the above procedure, when setting up the ESP32 board, we selected:

  [![arduino-wifizine-config-board](./images/arduino-wifizine-config-board.png)](./images/arduino-wifizine-config-board.png)

  ```
  Partition Scheme : Default
  ```

  The default partitioning scheme includes elements that are not necessarily required for Hot-spot zine, and the default partition configuration does have less room available for Zine content. (~ 1MB)

- So, by reconfiguring the Partition Scheme more efficiently, you may be able to upload a little more Hot-spot zine content. In this way, a capacity of about 1.9 MB can be used for Zine contents.

- Once you have completed this procedure, you may select,

  [![arduino-wifizine-custom-partition](./images/arduino-wifizine-custom-partition.png)](./images/arduino-wifizine-custom-partition.png)

  ```
  Partition Scheme : WIFI ZINE
  ```

- Work process

  - Download and install [the partition configuration file](https://raw.githubusercontent.com/applecargo/WifiZineThrowie/master/partition/wifi_zine.csv)

    Paste it into ~/Library/Arduino15/packages/esp32/hardware/esp32/1.0.1/tools/partitions

    [![arduino-partition-00001](./images/arduino-partition-00001.png)](./images/arduino-partition-00001.png)

    The '~/Library/' folder is a hidden folder in the Finder, so type Cmd-Shift-G and type in 'Library'

    [![arduino-partition-00002](./images/arduino-partition-00002.png)](./images/arduino-partition-00002.png)

    Then, double-click the 'Arduino15' folder as a normal folder

    [![arduino-partition-00003](./images/arduino-partition-00003.png)](./images/arduino-partition-00003.png)

    Move to the above position

    [![arduino-partition-00004](./images/arduino-partition-00004.png)](./images/arduino-partition-00004.png)

    Make it like this.

  - Edit the boards.txt file

    [![arduino-partition-00005](./images/arduino-partition-00005.png)](./images/arduino-partition-00005.png)

    Open the file boards.txt file located in the above location and add the next four lines marked with + (remove the + sign!)

    ```diff
    --- /Users/doohoyi/Downloads/Telegram Desktop/boards.txt
    +++ /Users/doohoyi/Library/Arduino15/packages/esp32/hardware/esp32/1.0.1/boards.txt
    @@ -52,6 +52,10 @@
     esp32.menu.PartitionScheme.min_spiffs.upload.maximum_size=1966080
     esp32.menu.PartitionScheme.fatflash=16M Fat
     esp32.menu.PartitionScheme.fatflash.build.partitions=ffat
    +esp32.menu.PartitionScheme.wifi_zine=WIFI ZINE
    +esp32.menu.PartitionScheme.wifi_zine.build.partitions=wifi_zine
    +esp32.menu.PartitionScheme.wifi_zine.upload.maximum_size=1048576
    +esp32.menu.PartitionScheme.wifi_zine.upload.maximum_data_size=2752512

     esp32.menu.CPUFreq.240=240MHz (WiFi/BT)
     esp32.menu.CPUFreq.240.build.f_cpu=240000000L
    ```

  - After restarting the Arduino IDE, select PartitionScheme as 'WIFI ZINE' during ESP32 DEV Module setup and compile.

### Uploading and publishing Hot-spot zine content

- Hot-spot zine content is stored separately from the running code. Therefore, it goes through a separate process from the usual Arduino IDE code upload process. To do this, you need to install a separate extension plug-in.

- Download and install [the ESP32FS plug-in](https://github.com/me-no-dev/arduino-esp32fs-plugin/releases)

  Create a folder called '~/Documents/Arduino/tools'

  [![arduino-esp32fs-00002](./images/arduino-esp32fs-00002.png)](./images/arduino-esp32fs-00002.png)

  Copy unpacked ESP32FS to here

  [![arduino-esp32fs-00003](./images/arduino-esp32fs-00003.png)](./images/arduino-esp32fs-00003.png)

  Be mindful with the construction of the folders. It should be installed as shown in the following figure. (Note also that the folder name is ESP32FS!)

  [![arduino-esp32fs-00004](./images/arduino-esp32fs-00004.png)](./images/arduino-esp32fs-00004.png)

  After restarting the Arduino IDE, verify that the plug-in installation was successful. If successful, you will see a menu called 'ESP32 Sketch Data Upload' added.

  [![arduino-esp32fs-00005](./images/arduino-esp32fs-00005.png)](./images/arduino-esp32fs-00005.png)

  When you run this menu, it will move all the files in the '~/Documents/Arduino/WifiZineThrowie/data' folder to the ESP32 module's web page store.

  [![arduino-wifizine-webpage-upload](./images/arduino-wifizine-webpage-upload.png)](./images/arduino-wifizine-webpage-upload.png)

  Please execute the upload. The color of the message output during upload is displayed in white instead of red.  While 'Connecting ...' displays, [press and hold the' BOOT 'button on the ESP board for one second](https://randomnerdtutorials.com/solved-failed-to-connect-to-esp32-timed-out-waiting-for-packet-header/).

  Screen when upload is completed successfully

  [![arduino-wifizine-webpage-upload-done](./images/arduino-wifizine-webpage-upload-done.png)](./images/arduino-wifizine-webpage-upload-done.png)

  Congratulations. We are all ready to produce / publish Hot-spot zine.

## Generic content example of Hot-spot zines

- Example 1 Text page

  - [Hello, Text?](https://github.com/applecargo/WifiZineThrowie/blob/master/data-text.zip?raw=true)

    - [Obtaining fonts](https://www.dafont.com/)

- Example 2 Images page

  - [Imaginary, world](https://github.com/applecargo/WifiZineThrowie/blob/master/data-image.zip?raw=true)

- Example 3 Sounding page

  - [Sound-world!](https://github.com/applecargo/WifiZineThrowie/blob/master/data-sound.zip?raw=true)

- Example 4 Hyper-linked pages

  - Looooong story! (TBD)

- Example 5

  - (advanced) WebSocket - socket.io + server-side programming @ arduino (TBD)

    - I have not tried it, but it must be possible. Let's create an example.

- Example 6 : Paper.js  (TBD)

- Example 7 : P5.js  (TBD)

- Example 8 : <http://molleindustria.github.io/p5.play/>  (TBD)

- Example 9 : Tone.js  (TBD)


## Play with shapes and materials

- Attaching a sensor

  - switch? G-sensor?

- Attaching something that moves/acts

  - motor? speaker?

## Thinking with locations / places

- Attaching to the steel structure of the street or space using magnets

## Contributing to the project

- By sharing ZINE content, you can share ideas and inspirations for others who are creating Hot-spot zines. It is better to tell us your background story, context, form and so on.
- If you have ideas on how to improve the various parts of the Hot-spot zine program, please send us a revision with PR.
- If you have any other thoughts or opinions, please email me. <mailto:pilotedeguerre@gmail.com>

## Thank you!

----

## What is a hot-spot zine?

### One line description

- A wireless communication and web service device designed to service an independent publications in webzine format when a smartphone attempts to log in to a hotspot

[![hotspot-zine-ssid](./images/hotspot-zine-ssid.jpg){:width="500px"}](./images/hotspot-zine-ssid.jpg)
[![hotspot-zine-login](./images/hotspot-zine-login.jpg){:width="500px"}](./images/hotspot-zine-login.jpg)

- [View more](http://pilote.byus.net/wpdiana/?page_id=1064)

### Preceding project

- [CaptiveIntraweb by AReResearch (Andy Reischle) @ 2015](https://github.com/reischle/CaptiveIntraweb)

  [![construction-overview](./images/areresearch/img4.png){:width="500px"}](./images/areresearch/img4.png)

### Components

- Tangible components
  - Espressif's ESP32 module
  - Power supply (battery or DC adapter)
  - (Optional) a case or a hull
  - (Optional) Magnets

  [![construction-overview](./images/areresearch/img1.png){:width="500px"}](./images/areresearch/img1.png)

  [![construction-overview](./images/areresearch/img2.png){:width="500px"}](./images/areresearch/img2.png)

  [![construction-overview](./images/areresearch/img5.png){:width="500px"}](./images/areresearch/img5.png)

  [![construction-overview](./images/areresearch/img6.png){:width="500px"}](./images/areresearch/img6.png)

  [![construction-overview](./images/areresearch/img7.png){:width="500px"}](./images/areresearch/img7.png)

  (These images are posted by Andy Reischle (AReResearch).)

- Intangible components
  - [ESP-IDF Development Environment](https://github.com/espressif/esp-idf/tree/master/components)
  - [ESP32 Arduino Compatibility Package](https://github.com/espressif/arduino-esp32)
  - [SPIFFS file system](https://github.com/espressif/arduino-esp32/tree/master/libraries/SPIFFS)
  - [ESP web server library](https://github.com/me-no-dev/ESPAsyncWebServer)
  - [A domain name server (captive portal)](https://github.com/espressif/arduino-esp32/tree/master/libraries/DNSServer)
  - Web page (Webzine)

  [![Wi-Fi-zine-stacks](./images/Wi-Fi-zine-stacks.png){:width="500px"}](./images/Wi-Fi-zine-stacks.png)

  - [More information](http://esp32.net/)
  - [The Wi-Fi stack is not open source](https://github.com/espressif/esp32-wifi-lib/issues/2)

### Limitations of Hot-spot zine platform that you should know

- Storage 2MB or less
- Slightly slower than a typical web server
- Somewhat unstable behavior compared to a typical web server (sometimes a system restart may be required)



## Making a Hot-spot zine


