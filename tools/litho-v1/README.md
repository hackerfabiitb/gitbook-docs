---
description: A direct-write photolithography system with 5um line/space under INR 2,00,000
---

# litho-v1

Our lithography system is based HackerFab CMU's Litho v2.1+ (which is their latest as of September 2026): [https://docs.hackerfab.org/home/fab-toolkit/patterning/lithography-stepper-v2.1+-build](https://docs.hackerfab.org/home/fab-toolkit/patterning/lithography-stepper-v2.1+-build)

## Intro

Lithography means writing patterns into stone (Greek: lithos: stone, graphy: to write). Lithography is used in microfabrication to create patterns of a circuit on silicon.\
Photolithography exposes the pattern of light onto a thin film of photoresist coated on the sample. For positive photoresist, the regions of resist exposed to light undergo a chemical change which makes them soluble in a developer.

Our photolithography system uses a DLP projector with a UV LED modification.

## Why DLP?

Masked lithography shines blanket light through a hard mask consisting of transparent and opaque regions. This is used for high-throughput, high-resolution patterning for mass-manufacture of Integrated Circuits. The mask is expensive and slow to make, hence unsuitable for rapid prototyping at a student level.\
The hard mask itself is made using a maskless lithography system, which can be of 2 types:

1. Writer: a beam of photons (laser writing) or electrons (EBL: electron beam lithography) is scanned across the sample. Extremely high-resolution (<10nm for EBL), but low-throughput (slow). Used in research. Requires extremely precise motion stages to deflect the beam.
2. DMD: uses a DMD chip ([https://en.wikipedia.org/wiki/Digital\_micromirror\_device](https://en.wikipedia.org/wiki/Digital_micromirror_device)) to selectively block or reflect regions of light from a light source. Does not need beam deflection motion stages, and is much faster than writers because it exposes a large (approx 10mm wide before demagnification) area in a single exposure. However, its resolution is limited by the DMD pixel pitch. It is the perfect compromise for DIY litho: low-cost albeit low-throughput and low-resolution

The DMD chip itself can be found in consumer DLP ([https://en.wikipedia.org/wiki/Digital\_light\_processing](https://en.wikipedia.org/wiki/Digital_light_processing)) projectors. The DLP projector uses 3 LED light sources (Red, Green, Blue) illuminating the mirror array (DMD) to form the image. This enables swapping the blue LED for a 405nm UV led, which is suitable for exposing photoresist. **This would not be possible in a regular LCD projector**, as each of the millions of pixels has individual R,G,B leds, which cannot be swapped out for UV.

The silicon microfabrication revolution enabled cheap production of MEMS devices, which in turn makes our lithography system inexpensive!

## Optical Specifications

LED Wavelength: 405nm\
Lens NA: 0.25\
DMD pixel pitch: TODO

## System Performance

line/space for nominal 5um/5um line array: 4um/6um\
isolated line widths: TODO\
XYZ stage repeatability, tiling error, overlay error: TODO

## Bill of Materials

INR 2 Lakh Budget

<table><thead><tr><th>Item Name</th><th>Cost (INR) as of August 2026</th><th data-type="content-ref"></th></tr></thead><tbody><tr><td>TI DLP Evaluation Module (DLPDLCR471TPEVM) from Mouser</td><td>1,10,000</td><td><a href="https://www.mouser.in/en/ProductDetail/Texas-Instruments/DLPDLCR471TPEVM?qs=DRkmTr78QAQsT6dpWa8zKg%3D%3D">https://www.mouser.in/en/ProductDetail/Texas-Instruments/DLPDLCR471TPEVM?qs=DRkmTr78QAQsT6dpWa8zKg%3D%3D</a></td></tr><tr><td>Edmund Optics Beamsplitter (25 x 25mm, 25R/75T, AR Coated)</td><td>6,357</td><td><a href="https://www.edmundoptics.in/p/25-x-25mm-25R75T-AR-Coated-Plate-Beamsplitter/45377">https://www.edmundoptics.in/p/25-x-25mm-25R75T-AR-Coated-Plate-Beamsplitter/45377</a></td></tr><tr><td>Edmund Optics 10X DIN Plan Commercial Grade Objective</td><td>20,178</td><td><a href="https://www.edmundoptics.in/p/10x-din-plan-commercial-grade-objective/5386">https://www.edmundoptics.in/p/10x-din-plan-commercial-grade-objective/5386</a></td></tr><tr><td>Basler ace scientific camera</td><td>10,000</td><td></td></tr><tr><td>XYZ Stage 40mm. (TODO ADD 60mm one here)</td><td>7,000</td><td></td></tr><tr><td>NEMA 28 Stepper x 3</td><td>2,100</td><td><a href="https://amzn.in/d/00fimvk9">https://amzn.in/d/00fimvk9</a></td></tr><tr><td>UV LEDs from ktron</td><td>TODO</td><td></td></tr><tr><td>Mounts: Metal &#x26; Machining</td><td>TODO</td><td><a href="https://github.com/hackerfabiitb/litho_machining_m27x1.5">https://github.com/hackerfabiitb/litho_machining_m27x1.5</a></td></tr></tbody></table>

## Software

| Sr No | Software Name  | Purpose                                            | Instructions                                                                       | Link                                                                                                                                                                                   |
| ----- | -------------- | -------------------------------------------------- | ---------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1     | Basler Pylon   | Receiving video feed from industrial camera        | Download the latest version of Pylon (the software suite, not the redistributable) | [https://www.baslerweb.com/en/downloads/software/?downloadCategory.values.label.data=pylon](https://www.baslerweb.com/en/downloads/software/?downloadCategory.values.label.data=pylon) |
| 2     | TI DLP EVM GUI | Controlling DLP LED intensities                    | DLPDLC-GUI, NOT Lightcrafter                                                       | [https://www.ti.com/tool/DLPDLC-GUI](https://www.ti.com/tool/DLPDLC-GUI)                                                                                                               |
| 3     | GIMP           | Open-source image editor for creating masks        |                                                                                    | [https://www.gimp.org/downloads/](https://www.gimp.org/downloads/)                                                                                                                     |
| 4     | OBS Studio     | viewing the video feed being sent to the projector |                                                                                    | [https://obsproject.com/download](https://obsproject.com/download)                                                                                                                     |

## SOP

These recipes are based on the ones developed at IITBNF ([https://www.iitbnf.iitb.ac.in/](https://www.iitbnf.iitb.ac.in/))

### Chemicals

1. S1813 PPR: Positive Photoresist: exposed parts are soluble in developer. [Datasheet](https://drive.google.com/file/d/1xYIi1hyWTzFgmqcuzrqd_HlrwxEy8HMW/view?usp=drive_link), [MSDS 1](https://drive.google.com/file/d/1EmSJbKPpif73l_fudvb6x7Dx4e-fZoJc/view?usp=drive_link), [MSDS 2](https://drive.google.com/file/d/1jNVW-7bWbhX3y3jYUYZ0rI_DoDHn2GJi/view?usp=drive_link)
2. LOR 3b: lift-off resist used for removing un-patterned metal after sputtering. Not photosensitive, but used to provide undercut (see[liftoff-and-undercut-in-deposition.md](../../fab-basics/liftoff-and-undercut-in-deposition.md "mention")). TODO Datasheet, MSDS
3. Mf319 Developer: removes LOR and exposed PPR. [Datasheet](https://drive.google.com/file/d/1XRJLITyVZ61BJQAi83fC5ZQ2qnj0IHLI/view?usp=drive_link), [MSDS](https://drive.google.com/file/d/1mUCmngaEArfdS0SmwkyfwTIn1UmCWHU0/view?usp=drive_link)
4. PG Remover: removes resists ignoring exposure. [Datasheet](https://drive.google.com/file/d/1LLKt0cq4torESFUye8tevUG-2PJ9fTeg/view?usp=drive_link), [MSDS](https://drive.google.com/file/d/1CHMThWx8GCKCOkcU-4_TkZDemfF-qgW7/view?usp=drive_link)

### PPR spin+bake recipe

| Sr. No. | Process     | Step    | Parameters                                              |
| ------- | ----------- | ------- | ------------------------------------------------------- |
| 1       | PPR coating | Step-1  | <p>Time = 10 s<br>RPM = 500<br>Acceleration = 250</p>   |
|         |             | Step-2  | <p>Time = 45 s<br>RPM = 4000<br>Acceleration = 2000</p> |
|         |             | Step-3  | <p>Time = 10 s<br>RPM = 0<br>Acceleration = 500</p>     |
| 2       | PPR Bake    | Heating | <p>Time = 3 min<br>Temperature = 90 °C</p>              |

### LOR spin+bake recipe

| Sr. No. | Process     | Step    | Parameters                                              |
| ------- | ----------- | ------- | ------------------------------------------------------- |
| 1       | LOR coating | Step-1  | <p>Time = 10 s<br>RPM = 500<br>Acceleration = 250</p>   |
|         |             | Step-2  | <p>Time = 45 s<br>RPM = 4000<br>Acceleration = 2000</p> |
|         |             | Step-3  | <p>Time = 10 s<br>RPM = 0<br>Acceleration = 500</p>     |
| 2       | LOR Bake    | Heating | <p>Time = 5 min<br>Temperature = 150 °C</p>             |

Exposure dose = 140mJ/cm^2 is the dose optimized by IITBNF. We don't have capability to measure intensity yet. See [#led-current-mapping](./#led-current-mapping "mention")

The optimal dose and develop varies with resist age, temperature, humidity etc. A reasonable range is 120-160mJ/cm^2 and 15s to 40s respectively. See&#x20;

### DLP usage

1. Turn on the projector power supply
2. Turn on the TODO switch
3. Open the TI DLP EVM GUI software: it should show the projector connected. If not: [#debugging](./#debugging "mention")&#x20;

#### Debugging

Debug > USB connection

Unplug, replug usb cable

remove HDMI cable

check Device Manager

TODO

#### LED current mapping

As discovered by TODO on the HackerFab Discord, the current shown in the software maps to actual LED milliamps by TODO formula

### Dose Matrix: how to develop a litho recipe for your setup

See [litho-performance.md](../../fab-basics/litho-performance.md "mention")

