# Preview #

**Note : This is not a tutorial. For detailed procedures, please visit [Vanilla Guide](https://khronokernel-2.gitbook.io/opencore-vanilla-desktop-guide/) instead.**

![png](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/pics/about.png)

# Specs #

![image](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/pics/peripherals.png)

CPU : i7 9700K

Motheroard : Gigabyte Aorus Elite Z390

VGA : Gigabyte RX5700 XT GAMING OC

RAM : 8Gx2 KLEVV CRAS X RGB 3200MHz

Power : Corsair RM850x


Wifi & BT Module : BCM943602CS

Cooler : Corsair H115i pro

Hard drive : Micron MX500 500GB (For MacOS) & ADAT Sx8200pro 512GB (For Windows bootcamp)

Chassis : BeQuiet! Pure Base 600

# What is Working #

External graphics card (with headless iGPU enabled)

![image](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/pics/GPU.png)

Audio (with soundcard device-id 0700000)

![image](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/pics/sound.png)


Wifi、Bluetooth : normal, Handoff、Sidecar、Airdrop、Find function flawlessly

![image](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/pics/airdrop.png)

NVRAM : normal, available to select boot hard drive via system preference -> startup disk


![image](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/pics/boot.png)

Power : Native Power management enabled

![image](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/pics/power.png)

# Issues #

Sleep & wake : unable to change internal bluetooth header directly under the main XHCI controller, need to add [SSDT-GRPW.aml](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/EFI/OC/ACPI/SSDT-GPRW.aml)
to make USB turned off in order to enable sleep (which means you gotta press the power button everytime to wake it)

# Things to beware #


+ [MemoryAllocation.efi](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/EFI/OC/Drivers/MemoryAllocation.efi) is mandatory for all z390 boards. Without this, iGPU cannot be enabled properly.

+ CFG must be unlocked in advance. Since this board doesn't have any BIOS options related to it, I turned to [this approach](https://khronokernel-2.gitbook.io/opencore-vanilla-desktop-guide/extras/msr-lock) instead.


+ For every Opencore updates, be sure to use the [comparer](https://github.com/corpnewt/OCConfigCompare) to check if your config.plist meets the correct format.


+ **DevirtualiseMmio** should be set to False, since the KASLR injection method can easily lead to booting failures. In fact, paired with [MemoryAllocation.efi](https://github.com/stanleyhi8888/Aorus-Elite-Z390-Opencore-EFI/blob/master/EFI/OC/Drivers/MemoryAllocation.efi), I am able to boot perfectly by adding _slide=1_ to **boot-args**.

# References #

[Best guide ever!](https://khronokernel-2.gitbook.io/opencore-vanilla-desktop-guide/)

[xjn's blog](https://blog.xjn819.com/)

[opencore officials](https://github.com/acidanthera/OpenCorePkg)
