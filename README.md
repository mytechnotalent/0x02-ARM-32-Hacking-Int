![image](https://github.com/mytechnotalent/0x02_arm_32_hacking_int/blob/main/RPI32AAHI.png?raw=true)

# 0x02_arm_32_hacking_int
ARM 32-bit Raspberry Pi Hacking Int example in Kali Linux.

<br>

## Join DC540 Discord [HERE](https://discord.gg/TC9V9RCr5U)

<br>

## FREE Reverse Engineering Self-Study Course [HERE](https://github.com/mytechnotalent/Reverse-Engineering-Tutorial)

<br>

## Schematic
![image](https://github.com/mytechnotalent/0x02_arm_32_hacking_int/blob/main/schematic.png?raw=true)

## Parts
[Raspberry Pi 4](https://www.adafruit.com/product/4292)<br>
[64GB Micro SD Card](https://www.amazon.com/SDSDQUA-064G-A11-Professional-MicroSDXC-formatted-recording/dp/106171327X)<br>
[Micro SD Card Reader/Writer](https://www.amazon.com/uni-Adapter-Supports-Compatible-MacBook/dp/B081VHSB2V)

## STEP 1: Download Kali Linux ARM Image - Raspberry Pi 32-bit
[Download](https://images.kali.org/arm-images/kali-linux-2020.4-rpi4-nexmon.img.xz) [https://www.offensive-security.com/kali-linux-arm-images/]

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

    printf("%i\n", x);

    return 0;
}
```

## STEP 6: Save File As - 0x02_arm_32_hacking_int.c [:wq]

## STEP 7: Build & Link
```
gcc -o 0x02_arm_32_hacking_int 0x02_arm_32_hacking_int.c
```

## STEP 8: Run Binary
```
./0x02_arm_32_hacking_int
10
```

## STEP 9: Run Radare2 - Debug Mode
```
r2 -d ./0x02_arm_32_hacking_int
```

## STEP 10: Run Radare2 - Debug Step 1 [Examine Binary @ Entry Point]
```
aaa
s main
vv
```
![image](https://github.com/mytechnotalent/0x02_arm_32_hacking_int/blob/main/1.png?raw=true)

## STEP 11: Run Radare2 - Debug Step 2 [Examine int]
```
q
[0x0041b50c]> pf C @0x0041b512
0x0041b512 = 10
```

## STEP 12: Run Radare2 - Debug Step 3 [Hack int]
```
[0x0041b50c]> wa mov r3, 0xd @0x00470512
```

## STEP 13: Run Radare2 - Debug Step 4 [Review Hack]
```
[0x0041b50c]> pf C @0x0041b512
0x0041b512 = 13
```

## STEP 14: Run Radare2 - Debug Step 5 [Hack Binary Permanently]
```
q
r2 -w ./0x02_arm_32_hacking_int
[0x000003fc]> aaa
[0x000003fc]> s main
[0x0000050c]> vv
```
![image](https://github.com/mytechnotalent/0x02_arm_32_hacking_int/blob/main/2.png?raw=true)
```
[0x0000050c]> wa mov r3, 0xd @0x00000512
q
```

## STEP 15: Prove Hack
```
./0x02_arm_32_hacking_int
13
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0)
