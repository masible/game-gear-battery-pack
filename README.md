# game-gear-battery-pack
Information on how to modernise a [Game Gear Battery Pack](https://segaretro.org/Battery_Pack)

October 2018: **This is a work in progress**

## Goals

- Can power an unmodified, or LCD-modded Sega Genesis Nomad, or Game Gear
- More battery life than the original pack (if it were still working)
- No cuts to the shell
- Reuse existing fixtures (power switch, charge LED)

## Early research

Until I can buy a [Sega Nomad Powerback](https://segaretro.org/Nomad_PowerBack) for my Sega Nomad (or mod the console to have internal batteries), I need a way to power the portable when playing on the sofa. Using a Game Gear Battery Pack as a stop-gap solution is a good option, as it's more common and thus much cheaper and easier to find (and Sega-branded to boot).

Unfortunately, those are now at least 25 to 30 years old, and the builtin NiCd cells are dead. And we can't just replace them with new NiCd cells, as those use [highly toxic Cadmium](https://en.wikipedia.org/wiki/Nickel%E2%80%93cadmium_battery#Environmental_impact), and we don't want to use a chemistry that will likely be completely forbidden in a couple of years. We also can't replace NiCd with LiPo batteries (as [this forum user naively did](XXX))! This needs a different charging circuit, otherwise we risk explosions. This [AdaFruit article](XXX) should give you the basics about rechargeable batteries.

The Game Gear battery pack [outputs 7.4V](XXX), the Nomad Powerback [outputs 7.2V](https://segaretro.org/File:Nomad_Instruction_Manual_Insert_Back.JPG), and both consoles can take 9V on their power inputs. So, we could settle on a 7.4V output, a common battery voltage, as our target voltage output.

**Note**: If you just want a way to power a Nomad and don't have a clip-on battery pack, maybe consider a good quality 5V USB power bank and [a USB mod](XXX), this would be much cheaper.

## Inside the device

After opening the battery pack with an 8-sized [pin spanner screwdriver](https://en.wikipedia.org/wiki/List_of_screw_drives#Spanner) (one screw visible, two hidden under the belt clip), we can find a pretty large circuit board, and a 6-Ni-Cd battery pack.

| Battery markings |
| --- |
| Cylindrical enclosed nickel-cadmium storage battery |
| Format: KR1.2SC-6E (RC04421) |
| Nominal electric voltage: 7.2V |
| Nominal capacity: 1200mAh |
| Manufacturing year and month: M0991S |

| Characteristic | Value |
| --- | --- |
| Length | 13cm |
| Diameter | 2.3cm |
| Weight | just shy of 300g |

## Parts

- Game Gear Battery Pack
- 7.4V LiPo charging module, USB input ([DFROBOT DF-DFR0564](https://www.dfrobot.com/product-1713.html))
- 2 x 18650 3.7V batteries (buy locally, or from a reputable source, otherwise you can forget about the rating being anywhere near close to reality)
- 2S 18650 "BMS" charger board
- USB breakout board (I used a USB-C one, as the port is reversible, but use micro-USB if you prefer)
- optional: a sheet of acrylic, use as support in place of the original PCB
- optional: DC splitter cable and appropriate male jacks, if you want it to power a Sega Nomad.

Depending on where you get the 18650 batteries, and not counting the battery pack, this all should come to about 40€/$45.

**Note**: that you shouldn't buy "RC" or "drone" batteries, those are made to discharge even when really low, so that the remote-controlled vehicle doesn't crash to the ground, at the expense of the battery's safety.

## Conclusion

TODO (mention weigth, expected battery life for a Game Gear or Nomad, charge time)

Possible enhancements:
- 2P2S configuration to use up all the space inside the pack, and double the capacity
- real USB Power Delivery charging circuit for faster charging
