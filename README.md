# OpenC64DiagCart
OpenC64DiagCart started as a fork of OpenC64Cart by SukkoPera [available at](https://github.com/SukkoPera/OpenC64Cart). The primary goal being to replace all the jumpers with a single rotary DIP switch while also retaining the ability to have one of the 8 image slots be used as a C64 Dead Test. 
 
![Board](https://raw.githubusercontent.com/TheSupremeMonkey/OpenC64DiagCart/master/doc/render-top.png)
 
### Summary
Most Commodore 64 diagnostic cartriges are a standard 8k image, but since the dead test can run without any ROMs it has to run in Ultimax mode. Since I wanted to keep this simple, I decided to try to use parts I already had. In the end I ended up using a 74LS02 quad 2-input NOR gate and a 4066 quad bilateral switch which are both spare parts I keep around for reparing Commdoe 64 motherboards. The 74LS02 is used to read the state of the DIP switch which is tied to the last 3 address pins (A13,A14, & A15) of the 27512. When all 3 pins are low the CE and OE pins on the 27512 are connected through a switch in 4066 to ROMH and the and GAME is set high. For any other combination of A13, A14, and A15 CE and OE are connected through a different switch on the 4066 to ROML and EXROM is set high. This means that the first image out of 8 on the 27512 ROM will automatically be in Ultimax mode and can run a dead test. All the other images can be any 8k cartridge image you want. 
 
### Configuration
 Comming soon...
 
### Thanks
While this is technically a fork of [OpenC64Cart](https://github.com/SukkoPera/OpenC64Cart), it was also very helpful to look at the design of Bwack's [Vers64Cart](https://github.com/bwack/Versa64Cart). A ton of credit also needs to go to the [World Of Jani](http://blog.worldofjani.com/) blog for both the [diagnostic images](http://blog.worldofjani.com/?p=164) and [code](http://blog.worldofjani.com/?p=1981), as well a ton of [documentation](http://blog.worldofjani.com/?p=879) on how these cartridges work. 

