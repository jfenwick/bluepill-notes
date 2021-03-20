# bluepill-notes
All this development is on Windows 10, in case the platform is important.

Here's a good overview.\
https://www.e-tinkers.com/2020/01/getting-started-with-stm32-and-things-you-need-to-be-aware-of/

Tutorial I started with.\
https://os.mbed.com/users/hudakz/code/STM32F103C8T6_Hello/

Lessons learned:\
Mbed online compiler is good for building a blink program to test if board is working.\
No USB programming out of the box. Hookup ST-Link programmer to jumpers with female-to-female cables. STM32 ST-LINK Utility for uploading a basic program or erasing a chip.\
No serial printing from the ST-Link programmer. Use an FTDI programmer to connect to separate serial port.\
Mbed Studio is an OK IDE to build programs in.

At one point I started the debugger on Mbed Studio and the board got stuck. I managed to erase the chip in STM32 ST-LINK Utility. This is why it's useful to be able to use the utility even if you mostly program the board throug the IDE.

Don't try to printf floats! I got bit by this one.
https://forums.mbed.com/t/printf-not-working-with-float-data-type/562

There are big differences between old versions of the Mbed API and Mbed 6.
For instance Serial is deprecated and will throw warnings when you use it.
It helps to look at this:
https://os.mbed.com/docs/mbed-os/v6.9/apis/index.html

Watch out for when people try to put units into variables. Allegedly the compiler can handle that but I found it to be a problem.

Servos:\
I decided a servo was a good place to start.\
Mbed has a lot of example code and libraries out there, but it usually takes more work than say Arduino to get examples going.\
I ended up using a modified version of Simon's library, but Khaled's tutorial was useful for learning about tuning.\
Initially I did it in Mbed Studio then ported to PlatformIO.\
https://os.mbed.com/users/4180_1/notebook/an-introduction-to-servos/\
https://os.mbed.com/cookbook/Servo\
https://os.mbed.com/users/simon/code/Servo/\
https://www.electronicshub.org/controlling-a-servo-motor-with-stm32f103c8t6/\
https://deepbluembedded.com/stm32-servo-motor-control-with-pwm-servo-library-examples-code/

Setting up PlatformIO:\
https://medium.com/@jobenas_25464/how-to-work-with-the-stm32-blue-pill-in-platformio-and-not-die-trying-1700250e54e2\
https://www.onetransistor.eu/2018/09/stm32-bluepill-dev-mbed-platformio-vscode.html

I decided to try PlatformIO because VSCode has become the most popular IDE. I seem to be sticking with it for now.

I'd like to try the JTAG debugger at some point:\
https://lujji.github.io/blog/installing-blackmagic-via-stlink-bootloader/

I may want to learn STM32Cube at some point:\
https://deepbluembedded.com/stm32-arm-programming-tutorials/

Flashing over USB that isn't Arduino?\
https://jeelabs.org/2017/09/enabling-usb-on-a-blue-pill/

A bare metal tutorial to try:\
https://hackaday.com/2020/11/17/bare-metal-stm32-from-power-up-to-hello-world/
