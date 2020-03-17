# Preview #

![png](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/pics/about.png)

# Spes #

![image](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/pics/peripherals.png)

CPU : i7 9700K

Motheroard : Gigabyte Aorus Elite Z390

VGA : Gigabyte RX5700 XT GAMING OC

RAM : 8Gx2 KLEVV CRAS X RGB 3200Mh

Power : Corsair RM850x


Wifi & BT Module : BCM943602CS

Cooler : Corsair H115i pro

Hardrive : Micron MX500 500GB (For MacOS) & ADAT Sx8200pro 512GB (For Windows bootcamp)

Chassis : BeQuiet! Pure Base 600

# What is Working #

External graphics card (with headless iGPU enabled)

![image](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/pics/iGPU.png)

Sound card (with device-id 0700000)

![image](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/pics/sound.png)


Wifi、Bluetooth : normal, Handoff、Sidecar、Airdrop、Find functions flawlessly

NVRAM : normal, able to select boot hardrive via system preference -> startup disk


![image](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/pics/boot.png)

Power : Native Power management enabled

![image](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/pics/power.png)

# What is not working #

Sleep & wake : unable to change internal bluetooth header directly under the main XHCI controller, need to apply SSDT-GRPW.aml
to make USB turned off in order to enable sleep (which means you gotta press the power button everytime to wake it)

# References #

[Best guide ever!](https://khronokernel-2.gitbook.io/opencore-vanilla-desktop-guide/)

[xjn's blog](https://blog.xjn819.com/)

[opencore officials](https://github.com/acidanthera/OpenCorePkg)
