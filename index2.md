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
In a web browser, type in 192.168.1.1 in the search bar. This will bring you to the Firmware Update page. where it says "choose file", choose the Open WRT firmware that we downloaded earlier. after that choose update firmware and located the firmware update file you downloaded.

## flashing pineapple

## Setting up the pineapple 



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
