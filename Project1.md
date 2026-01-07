
# Project 1 Pwnagotchi 
My first project that I wanted to tackle was the Pwnagotchi. A Pwnagotchi is a small penetration testing tool used for Wi-Fi packet sniffing and handshake capture. The way it captures these handshakes is when a client or phone attempts to connect or reconnect to a router for internet access. When they do connect, they perform an action called a four-way handshake with the access point. If the Pwnagotchi is listening at the right time and on the right channel, it can capture that handshake for later cracking.
The Pwnagotchi has another method of capturing handshakes if it cannot identify any clients attempting to reconnect to an access point. The Pwnagotchi will send out deauthentication (deauth) packets to force a client to reconnect, thus creating an opportunity to capture a handshake.
## Storage and processing
Captured handshakes are saved in the ".pcap" or ".pcapng" format under the directory "/root/handshakes".
## Offline Cracking
There are many tools available on the internet for cracking hash files. The most popular include Hashcat, Aircrack-ng, and John the Ripper. Furthermore, the most recognised wordlist used to crack these hashes is rockyou.txt.


### Step 1 Getting Components 
I managed to get all my components off amazon before they were listed as "unavailable".
*  Raspberry Pi Zero WH
*  PiSugar S (Battery)
*  Waveshare 2.13 inch E-ink Display V4
*  32 GB Micro SD card
*  SD card to USB adaptor

### Step 2 installing software
In order to flash the image onto the SD card, I needed a specific type of software that is used for flashing images onto memory cards. The software I chose was Balena Etcher.
Furthermore, the actual image that I used for this project is a modified version of the original image. The creator of this image is Jayofelony. I specifically made sure that I incorporated the 64-bit version of the image and not the 32-bit version.
#### Troubleshooting software 

### Step 3 physical connection and driver installation
Once the Raspberry Pi has its SD card installed, the next task is to plug the device into my computer with the help of a micro USB connector. The device will appear as a USB Serial Device (COM#) under the “Ports” tab within the Device Manager application on Windows. The COM number will be different on all computers, so it is important to correctly identify the specific USB device that has been plugged in. This can be verified by unplugging the device and noting which entry disappears from the Ports tab. When the drivers are installed, the USB Serial Device will change into a network adapter. This is extremely important, as there needs to be a serial connection made to the device in the future once the device is operational.

The link to the drivers is .......
Once the drivers are installed, they need to be extracted onto your desktop or whichever location is preferable. WinRAR is recommended for extracting files; however, any other extraction software can be used.
Once they are extracted, there will be two files called RNDIS. The file that needs to be installed appears as a blank file with a gear icon in the bottom-left corner. Right-click the file and, at the top, click on “Install”.
The installation will only take a few seconds. When connecting the Raspberry Pi back into the computer, it should appear as a network device. It should be called “USB Ethernet/RNDIS Gadget”.

### Setting up Network Configurations 
Now that the Raspberry Pi is a dedicated network device, it can be configured with an IP address. This can be accessed through the Control Panel by holding “Windows key + R” and typing “control”.
At the top right, there is a search bar. Type in “Network and Sharing” and then make your way to “Change adapter settings”. You can now access the IP settings of the Raspberry Pi by right-clicking it and selecting “Properties”.

The information will be as follows. 
IP address  10.0.0.1
Subnetmask  255.255.255.0

Leave the DNS setting for later as that will be changed later on. 

### Troubleshooting 
Make sure to enter the following commands into an administrator PowerShell session, as this will enable internet sharing for the Pwnagotchi.
"powershell -ExecutionPolicy ByPass -File .\win_connection_share.ps1 -SetPwnagotchiSubnet"
"powershell -ExecutionPolicy ByPass -File .\win_connection_share.ps1 -EnableInternetConnectionSharing"
Once these commands are executed within the administrator PowerShell session, internet sharing should be enabled for the Pwnagotchi. Just make sure that the Windows computer is restarted.

### installing screen 
Installing the screen was a bit tricky, as it required equal pressure to be applied on both sides of the screen, as well as making sure that you do not bend any of the I/O pins located on the Pi Zero.

### connecting to the Pwnagotchi 
The software needed for connecting to the device is “PuTTY”. This allows us to communicate with the Raspberry Pi and log in to the device. The default login credentials are
Username: pi 
Passwd: raspberry 

###Configuring pwnagotchi 
Once the connection has been established and the Raspberry Pi is accessed, we need to configure the default password so that it cannot be accessed by any unauthorized users. The command for changing the password is
"passwd pi

Next is changing the configuration settings.

We will use the command "sudo pwnagotchi --wizard" to start the configuration process.

It will ask if we want to restore the previous configuration; press N since we do not have an existing configuration.

The next question is about overwriting the current configuration file; press Y since we will be creating a new configuration.

Name your Pwnagotchi whatever name suits you.

It will then ask about the number of networks you would like to whitelist. These networks will not be targeted by the Pwnagotchi. In this case, I entered my home network’s SSID and MAC address.

Next, it will ask about Bluetooth tethering; enter N, as we will return to that topic once everything is set up.

Press Y for the screen being displayed, as this will allow the Pwnagotchi to show information on the physical device. For the type of display we are using, the display type is "waveshare_4". The preference for display color is purely cosmetic and can be changed later in the future.

Currently, the screen does not refresh fast enough for the Pwnagotchi to provide any meaningful information. We will configure a file so that the screen refreshes after a shorter amount of time.

Navigate to "cd /etc/pwnagotchi/" and edit the file using "sudo nano config.toml". In a space below the original text, add "ui.fps = 1". This will refresh the screen once every second. Press "Ctrl + X" and then press "Y" to save the configuration.

For these changes to be implemented, make sure to restart the device using the command "systemctl restart pwnagotchi.service".
## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
