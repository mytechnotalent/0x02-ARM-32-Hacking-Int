![image](https://github.com/mytechnotalent/0x02_arm_32_hacking_int/blob/main/RPI32AAHI.png?raw=true)

# 0x02_arm_32_hacking_int
ARM 32-bit Raspberry Pi Hacking Int example in Kali Linux.

## Schematic
![image](https://github.com/mytechnotalent/0x02_arm_32_hacking_int/blob/main/schematic.png?raw=true)

## Parts
[Raspberry Pi 4](https://www.adafruit.com/product/4292)
[64GB Micro SD Card](https://www.amazon.com/SDSDQUA-064G-A11-Professional-MicroSDXC-formatted-recording/dp/106171327X)
[Micro SD Card Reader/Writer](https://www.amazon.com/uni-Adapter-Supports-Compatible-MacBook/dp/B081VHSB2V)

## STEP 1: Download Kali Linux ARM Image - Raspberry Pi 32-bit
[Download](https://images.kali.org/arm-images/kali-linux-2020.3a-rpi3-nexmon.img.xz)

## STEP 2: Download balenaEtcher
[Download](https://www.balena.io/etcher)

## STEP 3: Flash Kali Linux ARM Image
[Watch YT Null Byte Video](https://www.youtube.com/watch?v=Jquf9BDm4iU&t=493s)

## STEP 4: Power Up RPI & Login
***POWER UP DEVICE AND LOGIN AS KALI AND SET UP SSH***

## STEP 5: Create File In VIM
```c
#include <stdio.h>

int main()
{
    int x;

    x = 10;

    printf("%i", x);

    return 0;
}
```
