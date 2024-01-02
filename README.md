# OmaFon

*OmaFon* is the project name for a video communication device that does not require any input from its user. The user being primarily elderly folk that cannot be bothered to learn the ways of WhatsApp and Skype on smartphones and possibly have difficulties operating mobile phones designed for older users.

*Oma* from the German word for grandmother and *Fon* being short for the German word *Telefon*. The English title can be thought of as **GrammyPhone**.

# Project description

Any kind of device that can be used to make a video call with the user that does not require interaction to operate. Interaction as in tapping on a screen or moving a mouse about.

## Why build such a device?

*Oma* lives around 180 km away. Visiting her takes the whole day, and we try to get around it once a month, but it is still too infrequent. Having a car that breaks down every so often does not help the case either. Having the ability for visual communication helps everybody sleep better, knowing she is well up, and makes virtual visits possible more often.

A digital screen that can be used to show pictures from travels or parties is a bonus.

## What is available?

*Oma* has a TV that she regularly uses for entertainment when she is not watching the neighbours from the window, and she is capable enough of switching between its channels to find the input for the digital receiver connected to it.

Ideally, having a Skype-like-setup built into the TV would be the ideal place. But a smart TV would potentially overcomplicate everyday use of the device.

## What is missing?

Internet connection and the necessary hardware.

## What could be used to accomplish the project idea?

A mini-PC without a mouse and keyboard connected to the TV via HDMI and is configured to run constantly with Skype in the foreground. Luckily, all of this is easily possible and is described in the next section.

Alternatively, any old tablet that comes with everything built in:
* Slot for a SIM card for 4G connectivity
* Integrated microphone and webcam

Though, the user in this case might have to be comfortable enough to handle such a device. Somebody who has never used any kind of device such as smartphones or tablets might have difficulties in doing so.

*Side note:* If the given tablet does not have a built-in 4G modem, you can always set up external ones.

# Gathering the Hardware

## Computer

A Raspberry Pi would have been a good hit if it weren't for two things:
* It needs to be a simple looking device where the on-off button can be spotted easily
  * Raspberry Pi model 5 is the first one to have a power button
* Easily accessible and replaceable in case it breaks down or 
  * Raspberry Pi models were difficult to come by in the recent past due to little availability

Additionally, the price should be fairly low for this kind of undertaking. The computer does not have to do too much of a heavy lifting, as it is only supposed to be able to handle video calls.

A few months prior, while looking for birthday gift ideas for a friend who is an avid gamer, I came across blog posts describing reusing old HP and Dell thin clients to install RetroPie to run emulators and play video games. This gave me the idea to look into such devices as an alternative to the Raspberry Pi.

After hitting up a local online market ([Willhaben](https://www.willhaben.at)), I came across a seller with a couple of pieces of an HP t610. The model was being sold with 32 GB SSDs in addition to the 2 GB flash memory for €19 per piece. After a bit of haggling, the seller was willing to sell two of the devices for €35. Unfortunately for him, he did not have €5 to change, so he agreed to my €30 offer.

![Great success!](https://media.giphy.com/media/a0h7sAqON67nO/giphy.gif)

### Computer details

The HP t610 comes with:
* AMD T56N APU (dual-core) with AMD Radeon HD 6320 graphics chip
* 2 GB DDR3 RAM at 1600 MHz
* Further details can be found on the [website](https://support.hp.com/gb-en/document/c03235347#AbT0)

Hopefully enough power to run a Linux distro and Skype!

## Webcam

Many webcams come with an integrated microphone. This simplifies the hardware set up. The two primary topics to keep in mind when selecting the webcam are:
1. Compatibility with the OS: Should be checked beforehand to make sure you are not buying a piece of hardware that cannot be used
2. The image quality it produces should not bring down the upstream network connection
    * A 720p camera produces 720p quality at most, while a 1080p camera might look better but might lead to worse performance during the calls via the mobile network
    * Higher resolution requires more bandwidth and if Skype or any other videotelephony app is not capable to provide it, the audio/video synchronisation goes awry and requires more processing to reduce the image quality on the sending side (i.e., the *OmaFon*) to keep A/V synchronised

The [Trust Trino HD](https://www.amazon.de/dp/B0093LON9Q?ref=ppx_yo2ov_dt_b_product_details&th=1) was on sale on Amazon at the time of putting together the set-up. A little digging through the [internet confirmed](https://www.spinics.net/lists/linux-media/msg183265.html) that the camera and microphone would work without problems.

## Audio/Video

The simplest yet: [DP to HDMI cable](https://www.amazon.de/dp/B0BWPZRPY7?psc=1&ref=ppx_yo2ov_dt_b_product_details) for 10€ on Amazon.

Both, audio and video, are played through the TV, so no additional speakers are necessary. Having the audio also come out through the TV, allows the user to finely tune the volume with the same buttons on the remote they are used to anyway.

## Internet Connection

If an internet connection is available, this section can be skipped. Some may be lucky in enough to live in a city where there is a Wi-Fi hotspot, or maybe a nice neighbour allows grammy to connect the client to their Wi-Fi access point for a plate of cookies every month.

In that case, a Wi-Fi adapter should be considered if the computer of choice does not come with an integrated one.

Grandmother lives in a rental house with no Wi-Fi connection nearby. A cable connection could be a good alternative to using a 4G modem, but the contracts often come with caveats such as one or even two year contract periods and turn out costlier. If 4G connection quality proves meagre, there is always the possibility to switch to a cable based internet provider.

I had tested the internet connectivity on my phone and was able to reach over 70 Mbit/s in multiple speed tests. Something must have changed in the recent months because the speed has dropped to 25 Mbit/s. But even that number is good enough to give it a try.

### 4G Modem

Once more, I hit up the local online market to check out 4G modems and came across a much promising model, Alcatel HH40V. These were listed for about €15-25. The closer people live to the city, the more expensive the offers.

The most important criteria for the modem was that it is not locked=in to a vendor! Otherwise, you have to either use a SIM card of that vendor or go through flashing the firmware or otherwise unlocking the device.

If you live in a society that has more than it needs, you will inevitably end up selling some of your stuff or even giving away the things you no longer require. Sometimes you are not quite aware of the fact that you have things lying around that you no longer make use of. Being in a chat group for bartering, where people exchange stuff they no longer need, is a good alternative to putting those things in online markets and dealing with incoherent requests by potential buyers.

Such was the place where my wife asked for a 4G modem and funnily enough, somebody had just the very same Alcatel HH40V I had my eye on. He wanted to give the modem away anyway and wanted at most a six-pack for it, and I had beers at home from the last party.

![High five!](https://media.giphy.com/media/l0ErFafpUCQTQFMSk/giphy.gif)

### SIM Card and Contract

This was the easiest one to select. I am using a SIM only tariff without a specific contract period. I can quit any time or even take my phone number to the next service provider if I chose so. I simply ordered a SIM card for telephony with a data plan, as the SIM contracts with only data plans seem to be more expensive.

That is €10 per month for 50 GB up to 300 Mbit/s (in theory). No activation cost or service fees.

The modem only supports CAT4 with up to 150 Mbit/s downstream. After running a few speed tests, the connection manages to get 25-30 Mbit/s which is enough for this kind of undertaking.

# Implementation

## Machine set up

The following guide assumes the user's machine is Windows based.

A requirement is to have a Skype account at the ready for the device.

### Operating system

1. Download [Linux Mint XFCE Edition](https://www.linuxmint.com/edition.php?id=307) (version 21.2 at the time of writing)
2. Run [Rufus](https://rufus.ie/en/) to put the downloaded ISO onto a thumb drive
3. Install OS on the device
   * Side note: Might require you to change the boot order settings in the BIOS
4. During the installation, create a user without a password (i.e., empty string)
5. In the command line, run: `sudo apt-get update && sudo apt-get upgrade -y`

### Skype

1. Install Skype as per [guide](https://www.linuxcapable.com/how-to-install-skype-on-linux-mint/)
    ```
    sudo apt install dirmngr ca-certificates software-properties-common apt-transport-https curl -y
    curl -fsSL https://repo.skype.com/data/SKYPE-GPG-KEY | sudo gpg --dearmor | sudo tee /usr/share/keyrings/skype.gpg > /dev/null
    echo deb [arch=amd64 signed-by=/usr/share/keyrings/skype.gpg] https://repo.skype.com/deb stable main | sudo tee /etc/apt/sources.list.d/skype.list
    sudo apt update && sudo apt install skypeforlinux
    ```
2. Log into Skype
   * **Important:** While logging in or registering in Skype, you will be asked for a keyring password. Make that password an empty string to allow for automatic start-up of Skype, as otherwise it will require user input every time!
3. Set up Skype to accept incoming calls with video
   1. Settings -> Calling -> Advanced
   2. Enable `Answer incoming calls automatically`
   3. Enable `Start my video automatically`
4.  Configure Skype to only accept calls from contacts:
   1.  Enable `Only allow Skype calls from contacts to ring on this device`

Skype should now be ready to go. Make sure you are one of the contacts and give it a ring, it should automatically pick up with video, no user input required!

### RustDesk

Seeing as this device is going to be deployed to a remote location, a form of remote administration is required. Such a tool also brings yet another bonus into play of being able to use the TV screen to show photos!

1. Download the latest release of [RustDesk](https://github.com/rustdesk/rustdesk/releases) with the name ending in `x86_64.deb`
2. Install the package: `sudo dpkg -i rustdesk-*x86_64.deb`
3. This may give you the hint, that the installation had issues due to missing dependencies. To install those missing dependencies, simply run: `sudo apt-get -f install`
4. Once RustDesk is installed, run and go settings by clicking on the pen next to the one-time password
   1. Click on `Unlock security settings` at the top
   2. In the **Permissions** section, enable `Enable remote configuration modification`
   3. In the **Password** section, select `Use permanent password` and click `Set permanent password`
   4. Make sure to use a safe password!
5. Test the connection from your own machine and store the credentials if required

The remote session can be used for many things. One bonus is that you can use the "share photo" functionality of your camera phone to send images directly to her via Skype, and then use the remote management session to show her those photos while you are on the mobile phone with her.

**Important note:** Using Skype for videotelephony and using the remote session at the same time might be a bit taxing for the weak CPU. Hence, the suggestion to use the mobile phone to talk her through your holiday photos.

If you do not wish to install a prying eye in your grandmother's home that automatically picks up calls without her knowledge, you could use the remote connection to be the gatekeeper as to who gets to chat to her via video calls.

## Deployment

1. Set up the modem with the SIM card
   1. Activation will require you to put the SIM card into a phone first
   2. Perform the activation procedure, e.g., sending the code via SMS to the provider
   3. Disable PIN authentication, this may be necessary as the modem cannot set the PIN
2. Wire everything up (modem to computer, computer to TV and webcam, and of course, the power plugs)
3. Explain to grandmother how to find the HDMI channel on the TV
4. Give her a test ring in Skype to make sure everything works

Ideally test the full set up beforehand, before deploying at grandmothers site to weed out potential remaining issues!

# Result

A happy old woman.

Merry christmas, Oma!

![Oma](oma.jpg)

## Processes

### Video Calling

1. Make sure you are in a quiet environment without background noise
    * **Important:** The microphone might pick up too much noise and make it difficult for grandmother to understand you
2. Call grandmother on the phone and ask whether she is available for a quick video chat
3. Let her switch the channel on the TV
4. End the mobile phone call and call her via Skype

### Slide Show

1. Send grandmother images via Skype
2. Call grandmother on the phone and ask whether she would like to see your latest holiday photos
3. Let her switch the channel on the TV
4. Dial in via RustDesk and double click the device
5. Click through the images you sent via Skype and explain to her on the mobile phone why there are more photos of the food you had than people you travelled with

# Total cost

|Part|Cost per item|
|--|--|
|Computer|15|
|Webcam|9|
|DP to HDMI cable|10|
|Modem|-|
|Ethernet cable|I have a few always lying around|
|**Total**|34|

The SIM contract being paid monthly, is excluded from this list.

# FAQ

> ***Q:** Why is it called **Oma**Fon and not something more generic to include > all genders?! Are you sexist?*
> 
> A: Yes.

> ***Q:** No, really?*
> 
> A: My wife's grandmother happens to be a woman for whom this was created.

> ***Q:** Grandmother always pulls the power plug after turning off the TV. The > computer is plugged into a different power outlet and yet it always changes > the resolution when the TV is turned on. How to fix this?*
> 
> A: Tell her to stop doing that.
> 
> If that does not help, then you will have to make the OS always stick to the > same resolution. In my case, the OS is using X as the display server and the > following steps fixed the issue:
> 1. `sudo nano /etc/X11/xorg.conf`
> 2. Paste the following:
>     ```
>     Section "Screen"
>         Identifier    "Default Screen"
>         Monitor        "Configured Monitor"
>         Device        "Configured Video Device"
>         DefaultDepth    24
>         SubSection "Display"
>             Depth    24
>             Modes     "1280x720" "1024x768"
>         EndSubSection
>     EndSection 
>     ```
> 3. Save and close the file
> 4. Reboot the machine

> ***Q:** What are you going to do with the second HP t610?*
> 
> A: Not sure yet. Do you happen to need one to build an OmaFon?