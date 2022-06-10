# Setup Raspberry Pi

Why would we want a hacking minimalistic setup on a Raspberry Pi? Mainly because it's low powered and highly mobile. In addition if used exclusively for hacking purposes then your personal information won't be there. So the purpose of this guide is to provide the absolute minimum and safest environment for hacking. It will not suite every scenario but if it's mainly scripting it should do the job just fine.

NOTE: during my setup I had to actually reinstall DietPi a bunch of times to get used to the options, navigation and also the sequence of steps. For example setting up the Network was a bit cumbersome. The most effective way I found was to start with network cable and when everything was ok, switch to Wi-fi.

Also you might want first attempt to try and install Anonsurf before anything else since it's the only "non-standard" application that is required and since it takes control of your network through IP tables etc you might want to check how to install it first. This is indeed the core of this guide. Anonsurf is what will provide the most basic layer of security through TOR navigation.

## Install DietPi on a clean SD card

DietPi allows you to customize what you want and we want a minimalistic installation. You can get the correct installation from their website: https://dietpi.com/

### Dietpi options

DietPi offers a comprehensive set of tools and applications we can add during installations. For start I would recommend the following and you can of course adjust according to your needs.

https://dietpi.com/docs/software/desktop/#mate

https://dietpi.com/docs/software/desktop/#chromium

https://dietpi.com/docs/software/desktop/#firefox


If you are not yet about deep diving into hacking you can simply add a TOR node and leave your RaspberryPi work 24/7 as a TOR node.
https://dietpi.com/docs/software/distributed_projects/#tor-relay. We don't want to have this installed if we are going to actually perform hacking. For that we want to have only Anonsurf (and a VPN). However if you want your Rpi working as TOR node first read this information: https://blog.torproject.org/tips-running-exit-node/

In a Raspberry Pi 3b+ this minimal setup works, but of course browsing should be done judisciously otherwise the resources will be depleted and our RPi 3b+ will soon stop responding. In addition we want this to be a minimalistic keeping anonimity as main goal so the less browsing we do the safer we are.

If new files are needed just use a normal USB stick to pass your files around, don't use browser, e-mail etc in this setup. Actually if you want an e-mail for hacking purposes needless to say you should create a separate one for that. Don't ever use your personal e-mail on hacking devices (RPi, docker image, etc).

## Install OpenJDK

You can chose any language/scripting as you like but we're going for Java so:

sudo apt update

sudo apt install default-jdk

java -version

that should get you going with java so you can write a piece of code and leave it running 24/7 with low power consumption.


## Get Anonsurf

Anonsurf comes originally with Parrot OS distribution but there's an available version that was prepared for running on Kali Linux. However we can also get it running on DietPi. Check the following resources

https://github.com/Und3rf10w/kali-anonsurf

https://www.geeksforgeeks.org/how-to-setup-and-use-anonsurf-on-kali-linux/


Anonsurf works also on DietPi. What you get won't be exactly the same as in the screenshots of the above tutorial and you won't get an UI tool to monitor the network status. But you get the command line giving you all that information.

IMPORTANT: we have to get Anonsurf running right from boot so we don't have our IP address being leaked. For that edit the file:

/var/lib/dietpi/dietpi-autostart/custom.sh 

and add the following line:

anonsurf start

You can also do this by following the steps on the Mate Desktop - if you don't know, you have to start dietpi as root and on the command line enter the command "startx" to bring Mate Desktop. You have to use the root user so that startx works correctly. Then you can get to the start script:

Applications -> System Tools -> DietPi-Config -> AutoStart Options -> Custom script (background, no autologin)

There you will be able to edit the custom.sh file

Reboot your Raspberry Pi and check if Anonsurf is working by running "anonsurf myip". You should get an IP address which is different than your LAN IP address. You can also play with the command "anonsurf change" which will shift to another TOR exit node so you'll get a new IP Adddress.

Most importantly to get a *real* feel of what your network is doing, we must have a check on DNS leak website. For example: https://www.dnsleaktest.com/. Go there and run some tests, namelly after a couple of reboots to make sure Anonsurf is running.


## Add a couple of extensions to Firefox

It's never too much if we are looking for even more security add some extensions to Firefox. Such as 

DuckDuckGo Privacy Essentials

Decenntraleyes

Cookie AutoDelete

uBlock Origin

HTTPS Everywhwere

NoScript

Privacy Badger


Check also the Privacy and Security definitions of your Firefox installation such as "HTTPS allways" mode - the above extensions HTTPS Everywhwere does the same. HTTP mode will be a hole in your browser navigation.


## Get a VPN

If you are doing advanced things that might get into trouble ( for example denial of service attacks is considered a crime in most jurisdictions) you will need to install a VPN. Here do your research and pick a payed one and - you guessed it - normally the most secure tend to be the most expensive. Check as many reviews as possible before choosing one.


That's it. With this setup we have a minimal hacking setup on a Raspberry Pi. It may take a many hours to get into the final setup that suits your needs but take your time and make sure you do your research. Check also how a VPN compares to TOR. There are VPN providers that allow TOR over VPN.

Again be carefull if you are just starting. Don't trust just the TOR network for anonymity. Entry and Exit nodes might still be monitored and although unlikely that's also a possibility. The absolute minimum is to use TOR.

## Most importantly: be ethical. Apply your hacking skills for the good of societey and don't harm others!!




