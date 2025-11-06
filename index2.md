---
layout: default
---

Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Aquiring Firmware
First we need a specific WI-FI adaptor, it must contain the RT5370 chipset so that it is compatable with out software  
Next is to get the pineapple software from a github page made by xchwarze (link). while on the page where is a link called "Downloads" and scroll until you find GLinet | GL-MT300N v2 | v19.07.7 

Next is ti head to the OpenWrt website and finding the right software for our pineapple. with all the list of devices. find the device labled MT300N v2 with the version being 19.07.7



## Physical and network configuration
in order to install the nessesary software onto the pineapple. it will need to be set in recovery mode. The can be done by first connecting the pineapple to a computer via ethernet. once that is done hold the reset button on the side of the pineapple whilst at the same time plugging the micro usb powercable into the device. while still pressing the reset button wait until the left and the middle LEDs are solid. by this point the pineapple is not in recovery mode.

while the pineapple is connected to a computer, search up "view network connections". We will need to identify what interface the mango is connected to wilst at the same time disableing the wifi on the device that the mango is connected to. once we have identifyed the mango device on our computer, we will need to head into its properties and find "IPV4". we will be changing the IP address of the mango to "192.168.1.2" with the subnet mask of "255.255.255.0" after that press ok. 

## flashing open wrt 
In a web browser, type in 192.168.1.1 in the search bar. This will bring you to the Firmware Update page. where it says "choose file", choose the Open WRT firmware that we downloaded earlier. after that choose update firmware and locate the firmware update file you downloaded. The update will start and the pineapple will start to flash its lights we must wait for both the left and right most lights are solid, this will take aproximately 2 minutes 30. 

## flashing pineapple
after the lights are solid you can resubmit the page to open the opewrt authorisation page. seeing this page means that the openwrt flashing to the pineapple device was a success. on this page, you are able to set a username and a password, it is recommended that you set your password with at least 12 characters with at least 1 capital letter, number and symbol. 

On the main page in open Wrt, hover over the systems tab on the top, and select from the rop down men "backup / flash firmware" and at the bottom clck on flash image and select the pineapple clone image. after a while a popup will ask if you would like to "keep settings and retain current configuraton, make sure to utick that box and click continue. this will take 3 mins, there will no indication that the update was completed on the website, just wait for the 3 lights on the pineapple to turn solid. after the lights turn solid we can not access the pineapple device. through the IP adress 172.16.42.1:1471
## Setting up the pineapple 
if you cant open the web page through the IP address, just go to the ip address setting for the pineapple on your laptop for computer and change the staticly assigned ip address that we gave to automatic, make sure that dnz settings is also set to automatic. After configuration, we should be able to access the ip address through the web. after contnuting through the pop up mesages, the last pop up will tell us that the "WIFI pineapple is still booting", this is when you will connect the wifi adaptor to the pineapple ans the npress the reset button just once. once done right the message should go away. with configurations you will need to manage some settings before continuing. make sure that you set a root password before continueing, furthermore you can set up a management SSID for the pineapple it can be what ever name we choose, further down the client and SSID filter settings both need to be set as "allow" as well as ticking both boxsfor the EULA. After logging into the pineapple with the root password you just created we now have access to the pineapple dashboard. 


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
