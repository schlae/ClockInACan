# Clock In A Can
## Customizable can and half-can style crystal oscillators

Have you noticed that it is getting harder and harder to find through-hole
oscillators in the metal can or half-can packages? The selection has been
shrinking as manufacturers discontinue entire legacy product lines.

Fortunately, there is a solution! The ClockInACan is a small circuit board
that is the same size as the oscillator and duplicates the same function
exactly. Just provide your own crystal of the desired frequency or a multiple
of the desired frequency, and set the three solder jumpers to select the
divide ratio.

![ClockInACan photo](https://github.com/schlae/ClockInACan/blob/master/images/ClockInACan.png)

![ClockInAHalfCan photo](https://github.com/schlae/ClockInACan/blob/master/images/ClockInAHalfCan.png)

Features include

* Wide +2V to +5.5V power supply range
* Logic-level enable pin with internal pullup
* CMOS-compatible output
* Selectable divide ratio of 1, 1/2, 1/4, 1/8, 1/16, and 1/32
* Crystal footprint fits through hole and many surface mount crystals
* Pins are breadboard compatible, and also fit in DIP sockets
* Pins have labels underneath the PCB for your convenience

[Here is the schematic](https://github.com/schlae/ClockInACan/blob/master/ClockInACan.pdf).

Fab files can be found here:
[ClockInACan fab files](https://github.com/schlae/ClockInACan/blob/master/fab/ClockInACanFab.zip)
[ClockInAHalfCan fab files](https://github.com/schlae/ClockInAHalfCan/blob/master/fab/ClockInAHalfCanFab.zip)

The basic bill of materials is below.

| Q | Designator | Description     | Mouser Part Number   |
| - | ---------- | --------------- | -------------------- |
| 1 | U1         | Oscillator IC   | 513-NJU6311RB2-TE1   |
| 1 | C1         | 0.1uF capacitor | 603-CC603KRX7R9BB104 |
| 0 | C2, C3     | Optional load caps |                   |
| 0 | R1, R2, R3 | Divider jumpers |                      |
| 1 | R4         | 0 ohm solder jumper |                  |
| 1 | Y1         | Crystal         |                      |
| 4 | J1, J7, J8, J14 | PCB pins   | 575-0542000150000    |

Board dimensions below. Order the board in whatever cool colors you like!

* ClockInACan: 0.8 x 0.5 inches
* ClockInAHalfCan: 0.5 x 0.5 inches

## Assembly Notes

I've found it easiest to install the pins *before* soldering any components
on the board. Make a jig out of a block of wood, like this:

![Block of wood with 4 holes for pins](https://github.com/schlae/ClockInACan/blob/master/images/Jig.png)

Then put the ClockInACan board on top, drop the four pins in place, and place
the whole thing into a small press or a bench vise, like this:

![Block of wood with ClockInACan in a vise](https://github.com/schlae/ClockInACan/blob/master/images/Jig2.png)

Apply enough pressure to push the pins into place, but no more.

Solder in C1 first, then U1 and R4. Set the R1, R2, and R3 jumpers to your
desired oscillator divider setting as follows:

| R1    | R2    | R3    | Setting |
| ----- | ----- | ----- | ------- |
| Open  | Open  | Open  | 1       |
| Short | Open  | Open  | /2      |
| Open  | Short | Open  | /4      |
| Short | Short | Open  | /8      |
| Open  | Open  | Short | /16     |
| Short | Open  | Short | /32     |

For your convenience, this table is reproduced on the bottom of the
ClockInACan PCB (although the ClockInAHalfCan does not have it due to space
constraints).

Install Y1, taking care not to short any component leads on the metal case of
the crystal. You may want to add Kapton tape to insulate the board from the
crystal. Large HC49 crystals can be folded over to save vertical space.

## Advanced Topics
The NJU6311 includes built-in load caps so C2 and C3 are not necessary unless
you have a particularly picky crystal. Similarly, R4 can be 0 ohms, but with
some crystals you may need to increase the resistance to reduce the drive
current. For further information see the [NJU6311 datasheet](https://www.njr.com/electronic_device/products/NJU6311.html).

## License
This work is licensed under a Creative Commons Attribution-ShareAlike 4.0
International License. See [https://creativecommons.org/licenses/by-sa/4.0/](https://creativecommons.org/licenses/by-sa/4.0/).


