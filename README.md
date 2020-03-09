# Mega Man: The Wily Wars Weapon Refill Patch
This patch for Mega Man: The Wily Wars on the SEGA Genesis makes weapon energy refill upon death in the whole game. This patch is build upon another patch, the SRAM+ hack by Ar8temis008.
A detailed description can be found [on the RomHacking page of this hack](http://www.romhacking.net/hacks/4760/), as well as an alternative download link.
In this README you will find further information on how this patch was made and reference material.

## Tools
- [The Exodus 2.1 emulator ](https://www.exodusemulator.com/downloads/release-archive), for disassembly, memory viewing, dissassembly, testing and even breakpoints.
- [LunarIPS](https://www.romhacking.net/utilities/240/), to create a patch file.

## Process
The Genesis is a system I had no experience with at all. First step then was reading up on the overall architecture (see the references below). I took note especially of how the memory is structured, common conventions and the registers and their usage.
Once I had a good feel for the architecture it was time to find a tool and get busy. Exodus turned out to be one of the few tools really available for genesis hacking. As all other hacks for Mega Man, the approach was to find offsets of the sought after values first. When those were found memory breakpoints were used to seek for possible in-game subroutines to do the work. In turned out there was one so now all that rested was constructing a patch code that calls this subroutine upon dying. Using step-by-step debugging it was assessed which registers are affected by the subroutine. The code to restore them to correct values after calling where looked up in assembly tutorials. Then the patch was applied and tested.

## References
In order to write the code a lot of knowledge was required. Here I list the sources specifically used for this project.
A big thanks for the people behind these to make Motorola 68000 Genesis programming more accessible.
