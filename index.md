---
layout: default
---

Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.


# Project 1 Pwnagotchi 
My first project that I wanted to tackle was the pwnagotchi. A pwnagotchi is a small penertration testing tool used for   Wi-Fi packet sniffing and handshake capture. The way it captures these handshakes is when a client or phone attempts to connect or reconnect to a router for internet. When they do connect they perform an action called a 4-way handshake with the access point. If the Pwnagotchi is listening at the right time and on the right channel, it can capture that handshake for later cracking.
The pwnagotchi had another method of capturing handshakes if it cannot identify any client attempting to reconnect to an access point. The Pwnagotchi will send out deauth packets to force a client to reconnect, thus creating an opportunity to catch a handshake. 
## Storage and processing
captred handshakes are saved as a ".pcap" format or ".pcapng" under the directory "/root/handshakes"
## Offline Cracking
There are many tools on the internet used for cracking hash files. the most popular include hashcat, Aircrack-ng and John the ripper. Furthermore the most recognised wordlist used to crack these hashes is rockyou.txt


### Step 1 Getting Components 
I managed to get all my components off amazon before they were listed as "unavailable".
*  Raspberry Pi Zero WH
*  PiSugar S (Battery)
*  Waveshare 2.13 inch E-ink Display V4
*  32 GB Micro SD card
*  SD card to USB adaptor

### Step 2 installing software
In order to flash the image onto the SD card I will need a specific type of software that is used for flashing images onto memory cards. The software I chose was Belena Etcher.
Furthermore the actual image that I used for this project is a modifyed version of the original image. The creator of this image is Jayofelony.... Specifically making sure that I incorporate the 64 bitversion
of the image and not the 32 bit version 
#### Troubleshooting software 

### Step 3 physical connection and driver installation
Once the raspberry pi has its SD card installed, the next task is to plug the device into my computer with the help of a micro SD card connector. The device will appear as a device called USB serial device COM# 
under the "Ports" tab within the device manager application on windows. The COM number will be differernce to all computers, its important to correctly identify if the plugged device is that specifyed USB device
this can be verified by plugging the device out and remembering which device is not present under the Ports tab. When drivers are installed, it will change the USB serical device into a network adaptor. This is extremely important since there needs to be a serial connection made to the device in the future once the device 
is operational.

The link to the drivers is .......
once the drivers are installed, they need to be extracted onto your desktop or which ever place is preferable. WinRAR is recommended for extracting files howevery, any other extraction software can be used.
Once they are extracted there will be 2 files called RNDIS. the file we need to install looks like a blankfile with a gear on the bottom left. Right click the file and up the top, click on install.
It will only take a few seconds to install. when connecting the raspberry device back into the computer, it should come up as a network device. it should be called "USB Ethernet/RNDIS Gadget".

### Setting up Network Configurations 
Now that the raspberry Pi is now a dedicated network device, it can now be configured with an IP address. this can be access though control panel by holding "windows key + r" and typing in "control".
On the top right, there is a search bar. type in "Network and sharing" then make you way to "change adaptor settings". you can now access to Ip settings of the raspberry Pi by right clicking it and choosing "Properties".

The information will be as follows. 
IP address  10.0.0.1
Subnetmask  255.255.255.0

Leave the DNS setting for later as that will be changed later on. 

### installing screen 
installing the screen was a bit tricky since it required equal pressure applied on both sides of the screen as well as 
making sure that you dont bend any of the IO pins located on the Pi Zero. 

### connecting to the Pwnagotchi 
The software we need for connecting to the device is "Putty". This will allow us to communicate with the raspberry pi and login to the device. The default login credentials are
Username: pi 
Passwd: raspberry 

###Configuring pwnagotchi 
once the connection has been established and the raspberry PI is accessed we would need to configure the default password so that it can't be access by any unauthoried users. The command for changing the password is 
"passwd pi

next is changing the configuration setting

we will use the command "Sudo pwnagothi --wizard" to start the configuration process 

It will ask if we want to restore the previous configuration, press N since we dont have an existing configuration 

Next question is about overwriting the current configuration file press Y since we will be creating a new configuraton 

Name you pwnagotchi to whatever name that suits you

It will then ask you about the number of networks you would like to whitelist. These networks will not be targeted by the pwnagotchi, in this case, i entered by home networks SSID and MAC address 

then it will ask you about bluetooth-tethering, enter N since we will touch back on that topic once everything is setup 

press Y for the screen being displayed since it will allow the pwnagotchi to display information on the physical device. For the type of display we are using the Display type is "waveshare_4". For the preferernce of display color, the choice is purely cosmetic and can be changed later in the furture. 

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
