# Poco F1 (beryllium) **Deep sleep** or **High idle drain** fix

## TL;DR: To long don't wanna read

- Flash the **latest** [NikGapps](https://sourceforge.net/projects/nikgapps/files/Releases/)
- Make sure to **edit** the **nikgapps.config** to avoid overwriting your ROM's default launcher (Usefull if your Custom ROM uses it's own custom launcher eg. EvoX, crDroid)
- **crDroid users** you could use this instead [crDroid NikGapps](https://sourceforge.net/projects/nikgapps/files/Elite-Releases/Gwolf2u/NikGapps-T/)
- Clean **Dalvik Cache** & **Cache** before you **reboot**

## Table of contents

- [Poco F1 (beryllium) **Deep sleep** or **High idle drain** fix](#poco-f1-beryllium-deep-sleep-or-high-idle-drain-fix)
  - [TL;DR: To long don't wanna read](#tldr-to-long-dont-wanna-read)
  - [Table of contents](#table-of-contents)
  - [Overview: The Issue / Problem details](#overview-the-issue--problem-details)
  - [Solution: What I did to try and fix it](#solution-what-i-did-to-try-and-fix-it)
  - [Note](#note)

## Overview: The Issue / Problem details

- ***Battery drain was high only when*** the ***screen was off***.  
[*0% Deep Sleep*](./Screenshot_20230724-005714_Evolution-X.jpg) ![deep sleep screenshot](./Screenshot_20230724-005714_Evolution-X.jpg)
- Lots of people not only from [EvoX Telegram](https://t.me/EvolutionXBeryllium) & [crDroid Telegram](https://t.me/crDroidPoco) are experiencing this issue and has been for a couple of weeks. (Some even tried to go back to their previous Custom ROM before trying out **EvoX** or **crDroid**) but the problem won't go away.
  
## Solution: What I did to try and fix it

- ***I'm not an Android developer so take this with a grain of salt***

1. I cleaned the type-C port.
2. I flashed SilverCore kernel but that didn't help.
3. I looked for answers:
   1. Clean the charging port or
   2. Change the *sub board* or *charging PCB board* (No follow up update 😐)
   3. Clear Google Play Services data (Tried it but the issue still exist)
   4. I found someone who said something about an event in the wakelock about the USB port reactivating every few seconds.

4. I checked the wakelock events (I have no idea what most of these are) ![wakelock screenshot](./Screenshot_20230724-010040_FKM.jpg) ![wakelock screenshot 2](./Screenshot_20230724-022807_FKM.jpg)

5. I flashed NikGapps latest A13 July 16 build *(It replaced the default Rom's Launcher because I forgot to edit the config file)*

   - Reset my battery usage
   - Turned off the screen for a few minutes, [the result:](./Screenshot_20230724-021352_Pixel.jpg)
  ![result](./Screenshot_20230724-021352_Pixel.jpg)
   - I reset the battery stats again, plugged in the charger, turned off the screen & that fixes the annoying issue, [the result:](Screenshot_20230724-032349_Pixel.jpg)
  ![battery drain, high idle, deep sleep fix](Screenshot_20230724-032349_Pixel.jpg)

## Note

- I noticed that more and more people started to encounter the problem. It becoming widespread day-by-day. If you think about it, people who mostly experienced it are the ***Google apps users***.
- It only happened to my phone last week, and my phone's always up-to-date, so it has to be with the recent updates right? ***(probably)***
- Flashing the full July 16 NikGapps build fixes it. ***(Coincidence?)***
