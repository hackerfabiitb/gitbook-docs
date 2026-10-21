---
description: Systematic operating procedure for litho-v1
---

# SOP

NOTE: read [.](./ "mention") first to understand the litho system.

## 1. Wafer Prep

Proceed to the next step if doing litho on an existing sample, eg on a sputtered film, or doing 2nd level litho. Else:

1. Cut a wafer piece with diamond scribe
2. Clean with acetone, then IPA, then dry with N2.

## 2. Spincoating

Use PPR\_spin+bake when doing isolated litho runs, or for etching.

Do LOR\_spin+bake then PPR\_spin+bake when doing litho then sputtering then liftoff.

### PPR\_spin+bake

| Sr. No. | Process           | Step    | Parameters                                              |
| ------- | ----------------- | ------- | ------------------------------------------------------- |
| 1       | PPR spincoating   | Step-1  | <p>Time = 10 s<br>RPM = 500<br>Acceleration = 250</p>   |
|         |                   | Step-2  | <p>Time = 45 s<br>RPM = 4000<br>Acceleration = 2000</p> |
|         |                   | Step-3  | <p>Time = 10 s<br>RPM = 0<br>Acceleration = 500</p>     |
| 2       | Pre-exposure Bake | Heating | <p>Time = 3 min<br>Temperature = 90 °C</p>              |

### LOR\_spin+bake

| Sr. No. | Process           | Step    | Parameters                                              |
| ------- | ----------------- | ------- | ------------------------------------------------------- |
| 1       | LOR spincoating   | Step-1  | <p>Time = 10 s<br>RPM = 500<br>Acceleration = 250</p>   |
|         |                   | Step-2  | <p>Time = 45 s<br>RPM = 4000<br>Acceleration = 2000</p> |
|         |                   | Step-3  | <p>Time = 10 s<br>RPM = 0<br>Acceleration = 500</p>     |
| 2       | Pre-exposure Bake | Heating | <p>Time = 5 min<br>Temperature = 150 °C</p>             |

### Dispensing Photoresist

1. **Turn on yellow lights and turn off white lights**
2. Take out S1813 photoresist from fridge and keep it out to reach room temperature
3. Set hot plate to recipe temperature and wait for it to stabilize.

The above steps take time so do them beforehand. Then:

1. Open spincoater lid. Replace the Al foil if it is dirty.
2. Place the sample centred on the O-ring.&#x20;
3. Put new tip on $$100\mu L$$ micropipette
4. Set it to $$100\mu L$$ . This is sufficient for even a 2 inch wafer.
5. Remove the Al foil and open the cap of the resist.
6. Press the pipette plunger. Dip only the tip of the pipette into the liquid. release the plunger
7. Move the tip over the sample. As you dispense move the tip around so the droplets cover the entire wafer
8. Press the slider to release the tip into a garbage bag.
9. Close the spincoater lid.
10. Start the preloaded recipe.
11. Bake according to the recipe. Keep a petri dish over the sample to prevent dust falling.
12. Lower the litho chuck in software (see below)
13. place the sample on the litho chuck



See [https://youtu.be/Jfqafjt4q6U](https://youtu.be/Jfqafjt4q6U) for how to use a pipette properly.

## 3. Litho

### Startup

1. Turn on the PC and monitor
2. Turn on the XYZ stage power supply
3. Plug in the camera USB cable.
4. Turn on the projector power supply mains
5. Open the DLP EVM GUI software, go to Display > Dynamic black > turn red on and drag the slider to the lowest power (101)
6. Turn on the LEDs switch on the projector PCB. this should turn on all 3 LEDs, which you can see glowing. If not, see [#debugging](sop.md#debugging "mention")
7. Immediately click "Set" in the software which keeps only the red LED on\
   **NOTE: do not keep the UV LED on for extended periods of time, it will burn.**
8. Open vscode in `Desktop\litho-control` , open the terminal, and run `.\ui\start.ps1` . Also keep claude code window in vscode open.



### litho-control software

1. Check that the projector, camera and Arduino all show connected
2. Focusing
   1. Click "go to focus" to move to a previously saved focus.
   2. Else, click autofocus with a suitable range and step size.
   3. Else, click the checker button to project a pattern for focusing, and move Z in steps of 500 to 100 to 10 to home in on the focus.
3. Click the TODO button to crop the camera view to the exposure field.

Use "optical tracking" to track features as the stage moves.

Run "Scan" to move the stage and get a wide-field scan.



### Exposure

Ask claude code to run an exposure sweep, which moves and exposes the same pattern for different durations.

There are pre-existing resolution tests in the `patterns` folder. Use claude code for making new resolution tests or custom text patterns.

Good exposure time is around 90s. Sweep from 30s to 120s.



## Development

1. Fill developer in a petri dish, and DI water in a beaker.
2. Dip the wafer in the developer for 20s, keeping it held with tweezers throughout.
3. Immediately immerse it in water and move it gently, to flush the developer out.
4. Dry with N2. The pattern should appear as a small rectangular mark on the wafer.
5. Put under microscope, or use the Scan feature of litho, to inspect the pattern.
6. Repeat from step 2, developing in 10s increments.

See [litho-performance.md](../../fab-basics/litho-performance.md "mention") for what a "good" exposure+development should look like.

**Remember to send developed images on Discord on the #litho-v1 channel before shutdown.**



The table of images formed from sweeping exposure and development on a give sample is called the **dose matrix.**



## Shutdown

(reverse order of [#startup](sop.md#startup "mention"))

1. close litho-control software and DLP EVM GUI software
2. turn off the LED switch and mains of the projector
3. unplug the camera USB cable to prevent overheating
4. turn off the XYZ stage power supply.

## Projector Debugging

Debug > USB connection

Unplug, replug usb cable

remove HDMI cable

check Device Manager

TODO

***

Note: these recipes are based on the ones developed at IITBNF ([https://www.iitbnf.iitb.ac.in/](https://www.iitbnf.iitb.ac.in/))
