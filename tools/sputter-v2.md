---
description: This is the official IITB documentation for the sputter
---

# sputter-v2



***

### Table of Contents

1. Introduction
2. What is a Sputter Coater? How does it work?
3. Bill of Materials (BOM)
4. Resources
5. Safety
6. Subsystem Build Instructions
   * Power Supply
   * Vacuum System
   * Chamber
   * Magnetron
   * Gas Flow System
7. Standard Operating Procedure (SOP)
8. Startup / Shutdown Checklists
9. Automation
10. Software
11. Improvements
12. Troubleshooting & Failure Modes
13. Glossary
14. India-Specific Sourcing Notes
15. To-Do / Missing Content
16. Revision History

***

### Introduction

This document describes the design, construction, and safe operation of a DIY magnetron sputter coater built primarily from salvaged and locally available components (with some imported fittings). The system is intended for depositing thin metal films onto substrates under vacuum using DC magnetron sputtering with argon process gas.

**Goals of this documentation**

* Enable a competent person with basic electronics, machining, and vacuum experience to rebuild or maintain the system.
* Provide sufficient safety information so the system can be operated without external assistance once built.
* Serve as the single source of truth for the project (GitBook / internal wiki).

**Audience**

* Makers, student teams, and small research groups with access to a workshop and basic high-voltage / vacuum safety training.
* Not a commercial product manual. Treat every high-voltage and vacuum section with extreme caution.

***

### What is a Sputter Coater? How does it work?

Sputtering is a Physical Vapor Deposition (PVD) technique used to deposit thin films of material onto a substrate.

**Basic process**

1. A vacuum chamber is evacuated to a low base pressure (typically 10⁻⁵ – 10⁻⁶ mbar or better) to remove residual air and water vapor.
2. An inert process gas (almost always argon) is introduced and the pressure is stabilized in the 10⁻³ – 10⁻¹ mbar range.
3. A high negative voltage (typically –300 V to –800 V or higher) is applied to a target made of the material to be deposited (the cathode). The chamber walls or a separate anode are at ground.
4. The electric field ionizes some of the argon atoms, creating a plasma (visible as a characteristic glow).
5. Positive argon ions (Ar⁺) are accelerated toward the negatively biased target and strike it with high kinetic energy.
6. Momentum transfer ejects atoms from the target surface (“sputtering”). These neutral atoms travel through the chamber and condense on the substrate, forming a thin film.

**Why “magnetron” sputtering?**\
In a simple diode sputterer the plasma density is low and deposition rates are slow. A magnetron places permanent magnets behind the target so that the magnetic field is parallel to the target surface (usually in a closed loop / “racetrack”). Electrons are trapped in helical paths near the target by the **E × B** drift. This dramatically increases the ionization probability of argon, producing a dense plasma localized just above the target. Result: higher deposition rates at lower pressures and lower voltages, with less substrate heating.

**Key operating regimes in this build**

* Plasma strike pressure: \~0.1 mbar
* Typical sputtering pressure: 0.01 – 0.001 mbar
* Pressure is maintained dynamically: turbo pump runs continuously while argon flow is adjusted via the mass-flow controller (MFC).

**Placeholder — Performance numbers**\
_\[Add measured base pressure, typical deposition rates for common targets (Au, Ag, Cu, etc.), and any film characterization data once available.]_

***

### Bill of Materials (BOM)

> **Placeholder section — Master table still incomplete.**\
> Populate the table below with every major component. Include quantity, approximate cost (INR preferred), source/link, and notes.&#x20;

| Subsystem | Component                                                | Qty | Approx. Cost (INR) | Source / Notes                        | Status |
| --------- | -------------------------------------------------------- | --- | ------------------ | ------------------------------------- | ------ |
| Vacuum    | Rotary vane pump                                         | 1   | \~50,000           | Local vacuum equipment supplier       | Known  |
| Vacuum    | Turbomolecular pump                                      | 1   | TBD                |                                       | TBD    |
| Vacuum    | Pirani gauge head + controller                           | 1   | TBD                | KF16                                  | TBD    |
| Vacuum    | Penning gauge head + controller                          | 1   | TBD                | KF25                                  | TBD    |
| Vacuum    | KF / ISO / CF fittings, adapters, O-rings, Viton gaskets | —   | TBD                | Various                               | TBD    |
| Chamber   | SS cylinder + flanges                                    | 1   | TBD                | Local steel vendor + laser cutting    | TBD    |
| Chamber   | Top & bottom plates                                      | 2   | TBD                |                                       | TBD    |
| Chamber   | Viewport glass + flange                                  | 1   | TBD                |                                       | TBD    |
| Chamber   | PEEK screws                                              | set | TBD                | Non-conductive top-plate mounting     | TBD    |
| Power     | Variac (0–230 V)                                         | 1   | TBD                |                                       | TBD    |
| Power     | Microwave oven transformer                               | 1+  | Salvaged           | Local appliance repair shops (Mumbai) | Known  |
| Power     | HV diodes + capacitor                                    | —   | Salvaged / order   | Microwave rated                       | TBD    |
| Power     | HV-rated gloves (≥1000 V)                                | 1   | TBD                |                                       | TBD    |
| Magnetron | Mild steel plate (nickel plated)                         | 1   | TBD                | Electroless Ni plating                | TBD    |
| Magnetron | Magnets, cooling if used                                 | —   | TBD                | Follow CMU geometry                   | TBD    |
| Gas       | Argon cylinder + regulator                               | 1   | TBD                |                                       | TBD    |
| Gas       | Mass Flow Controller (MFC)                               | 1   | TBD                | Second-hand (eBay etc.) preferred     | TBD    |
| Gas       | VCR / NPT / KF converters + gaskets                      | —   | TBD                | Often imported or machined            | TBD    |
| Misc      | High-voltage wiring, grounding plate, enclosure          | —   | TBD                |                                       | TBD    |

**Placeholder — Full BOM table**\
_\[Complete the table with exact part numbers, links, lead times, and total estimated budget.]_

***

### Resources

* **Magnetron design reference**: Carnegie Mellon University (CMU) published sputter documentation\
  **Placeholder link** — _\[Insert actual CMU magnetron / sputter documentation URL once confirmed.]_
* Vacuum fundamentals textbook referenced in notes as “Fifer”\
  **Placeholder** — _\[Confirm exact title/author. Common alternatives: “Foundations of Vacuum Science and Technology” (Laﬀerty), Leybold “Fundamentals of Vacuum Technology”, or Berman “Vacuum Engineering Calculations”.]_
* Swagelok fitting selection guides and videos (search “Swagelok VCR”, “Swagelok KF”).
* O-ring groove design: ISO standards for vacuum O-ring grooves (search “ISO vacuum O-ring groove design”).
* Flange standards: KF/NW, ISO-K, ISO-F, CF (ConFlat) comparison charts (many free PDFs from vacuum component vendors).
* MFC gas conversion factors: Brooks Instrument, MKS, or equivalent manufacturer tables (Argon GCF ≈ 1.39–1.40 relative to N₂).

**Placeholder — Additional links**\
_\[Add direct links to specific YouTube videos of the power-supply build, Swagelok tutorials, and any internal photos/diagrams once uploaded.]_

***

### Safety

High voltage, vacuum, and pressurized gas are all present. Treat all three with equal seriousness. **A single careless action can be fatal or destroy expensive components.**

#### High Voltage

* Always wear high-voltage-rated gloves (rated for at least 1000 V) when working on or near the power-supply section.
* Never touch live components. Assume everything is live until proven otherwise with a multimeter.
* Before handling any capacitor, **discharge it** by shorting its terminals with insulated high-voltage-rated tools, then verify zero voltage with a digital multimeter (DMM).
* Be extremely careful about accidental shorts. Keep the work area clear of conductive objects.
* Mount the variac and enclosure to a common grounded metal plate. Connect the AC plug ground pin to the enclosure. Ground one side of the high-voltage capacitor to the enclosure body.

#### Vacuum / Pressure

* Prefer metal chambers. Avoid glass jars for anything beyond early low-pressure prototyping; if used, enclose them in a protective housing against implosion.
* **Hard cutoff: treat 1 mbar as the absolute maximum pressure while the turbo pump or Penning gauge is operating.** If pressure is rising toward or above this value, stop argon flow immediately.
* Never vent the chamber to atmosphere while the turbomolecular pump or Penning gauge is on.
* The Penning gauge must **only** be switched on after the Pirani gauge indicates a safe low pressure. Powering a Penning gauge at high pressure will cause internal arcing and permanent damage.\
  **Exact interlock threshold (TBD)** — typical industry practice is often around 10⁻² mbar or lower; confirm with the specific gauge controller manual and mark the value here once verified.
* Turbo pump inlet path must be short and direct (see Vacuum System section).

#### Gas Handling

* Argon is inert but can displace oxygen in a confined space. Ensure good ventilation.
* Always use the correct regulators, fittings, and single-use VCR gaskets.
* Double-check male/female compatibility at every joint.

#### General

* Only trained personnel should operate the system.
* Keep a multimeter, HV-rated tools, and a fire extinguisher appropriate for electrical fires nearby.
* **Placeholder — Lab / institutional requirements**\
  _\[Add any required electrical safety sign-off, vacuum safety training, or local regulations that apply in your institution.]_

***

### Subsystem Build Instructions

#### Power Supply

Components can be salvaged from microwave ovens with strict precautions.

**Precautions when salvaging from a microwave**

1. Discharge the high-voltage capacitor completely before touching anything. Short the terminals with insulated tools, then verify zero volts with a DMM. Wear ≥1000 V rated gloves.
2. The magnetron tube itself often has a beryllium-oxide ceramic coating that is toxic if scraped or powdered. Handle carefully; do not drop or abrade it.

**Circuit topology**\
Variac (0–230 V AC) → Microwave oven transformer (step-up ≈ ×10) → Full-wave rectifier (HV diodes + capacitor) → High-voltage DC output to magnetron cathode.

* **Variac**: Throttles input voltage, giving roughly 0–2 kV AC at the secondary of the microwave transformer.
* **Microwave transformer identification**: Primary has lower DC resistance and usually two accessible terminals. Secondary has higher resistance; one end is often the core / ground reference. Accessing the secondary terminal may require polishing the casing or using a mounting hole.
* **Rectifier**: Use microwave-rated HV diodes and capacitor. A single microwave usually supplies only one diode — order spares. Transformers are harder to source; appliance repair shops that service microwaves are a good local source (successfully used in Mumbai).
* **Grounding**: Mount variac and enclosure to the same metal plate so the enclosure is grounded. Ground one terminal of the capacitor to the enclosure. AC ground pin → enclosure.

**Placeholders**

* _\[Circuit diagram: variac → transformer → rectifier → grounding.]_
* _\[Photos of each subsection and of the open-table prototype, including any relevant incident notes.]_
* _\[Link to all related build videos.]_
* _\[Photo / product link for the exact HV gloves used.]_

#### Vacuum System

**Pump configuration**\
Rotary vane pump → hose → turbomolecular pump → chamber.\
The rotary pump roughs the system through the turbo; once pressure is low enough the turbo is started.

> Note: This is a non-standard arrangement. In many professional systems the main chamber stays under continuous high vacuum and samples are introduced via a load-lock. The present design cannot hold the chamber at low vacuum independently of the turbo.

**Two flow regimes**

1. Viscous / continuum regime — molecules collide with each other; rotary pump is effective.
2. Molecular flow regime — molecules travel independently; turbo pump is required.

**Turbo pump plumbing**\
The turbo does not “suck”; its blades physically impart momentum to molecules. Keep the path from chamber to turbo inlet short, direct, and preferably straight or gently curved. Avoid long or convoluted hoses.

**Sealing principles**

* Two flat surfaces always have microscopic gaps → a soft gasket (Viton O-ring or flat gasket) fills them under compression.
* **KF (NW) flanges**: O-ring + clamp.
* To seal a component to a flat plate: machine a groove or use a gasket + perimeter screws that provide even compression.
* **ISO flanges**: ISO-K (clamp) and ISO-F (bolt).
* **CF (ConFlat)**: knife-edge + copper gasket (metal seal).

In this build an ISO-to-CF adapter was used; a Viton gasket was cut to sit on the CF knife-edge.\
**Lesson learned**: An ISO-K to ISO-F adapter would have been cleaner and fully Viton-compatible.

**Gauges**

* Pirani gauge (accurate roughly down to 10⁻³ mbar) — KF16 in this build (reducer used).
* Penning (cold-cathode) gauge for lower pressures — KF25.
* Each gauge needs its own head **and** controller.
* **Critical interlock**: Penning only after Pirani reads safely low. Exact threshold still TBD — mark it here once measured / confirmed from the gauge manuals.

**Placeholders**

* _\[Diagram of short turbo-to-chamber geometry.]_
* _\[Photos of KF assembly, O-ring vs gasket, KF16/KF25.]_
* _\[Exact Penning interlock pressure.]_
* _\[Verification of Viton-on-CF description and of the exhaust-line wording.]_

#### Chamber

Three main parts: top plate, cylindrical body, bottom plate.

**Material & thickness**

* Stainless steel preferred, minimum 8–10 mm wall thickness (conservative; no rigorous calculation was performed).
* Top/bottom plates may be steel or aluminum if using gasketed bolted joints. Welded flanges require matching steel.

**Fabrication philosophy**\
No welds on any vacuum-sealing surface. All welds are purely structural and located on the outside of the cylinder side-wall.

Body fabrication sequence:

1. Cut SS pipe to length (ID sized for required working volume).
2. Laser-cut or CNC flanges (rings) matching the pipe OD with margin for screw holes.
3. Weld flanges to the **outside** of the cylinder side walls only.
4. Mirror-polish all vacuum-facing surfaces (inner walls + flange faces) to reduce outgassing.

Top & bottom plate sealing:

* Matching bolt circles + O-ring groove slightly inboard of the bolts, just outside the chamber ID. Follow ISO O-ring groove guidelines for stretch and compression.

**Viewport**\
Mounted through the top plate (side viewport impossible without sealing welds).\
Sequence: groove → O-ring → glass → clamping flange → bolts.

**Electrical isolation**\
Top plate and body are at different potentials → use non-conductive **PEEK screws**.\
All mounting holes are blind tapped holes (through-holes would leak). Vented screws are recommended for higher-performance systems but were not required here.

**Placeholders**

* _\[Diagrams showing weld locations (structural only).]_
* _\[O-ring groove relative to chamber ID.]_
* _\[Step-by-step viewport assembly photos.]_
* _\[Details of salvaged KF-to-bolt-flange adapter (Aryamman).]_

#### Magnetron

Design closely follows CMU’s published documentation (**link TBD**).

**Material choice**

* Mild steel is magnetic (required) but rusts → outgassing risk.
* Stainless is non-magnetic.
* Solution used: mild steel plate with **electroless nickel plating**. Sand off existing rust, plate immediately before fresh rust forms.\
  Do **not** use powder coating or galvanizing — they are not vacuum-compatible.

**Placeholders**

* _\[Actual CMU hyperlink.]_
* _\[Photos of the finished magnetron.]_
* _\[Full source list / citations for the geometry.]_
* _\[Cooling details if water cooling is used.]_

#### Gas Flow System

1. **Estimate required flow**\
   Based on chamber volume, turbo speed, and target pressure.\
   Strike at \~0.1 mbar, then reduce to 0.01–0.001 mbar for sputtering. Pressure is a dynamic balance between continuous turbo pumping and continuous argon inflow.
2. **Select MFC**\
   Second-hand units are cost-effective. Each MFC is calibrated for a specific gas. Use manufacturer gas conversion factors (GCF) to operate with argon if the unit was calibrated for another gas (e.g. N₂ or O₂). Typical GCF for Ar relative to N₂ is ≈ 1.39–1.40. Accuracy is reduced (±5 % typical) when using conversion factors.
3. **Argon supply**\
   Cylinder + regulator. Choose tubing (metal or plastic) compatible with the regulator outlet. MFCs almost always use VCR fittings → NPT-to-VCR or push-fit-to-VCR converters are commonly required. VCR gaskets are single-use (plastic deformation).
4. **MFC to chamber**\
   VCR → KF adapter + KF size reducer if needed. Always verify male/female gender at every joint.

**Placeholders**

* _\[Block diagram of entire gas path with fitting call-outs.]_
* _\[Links to MFC, argon, fittings, Fifer textbook, and GCF explanation.]_
* _\[Swagelok reference videos.]_

***

### Standard Operating Procedure (SOP)

**Assigned to Aryan in the original notes.**

**Placeholder — Full SOP**\
_\[Aryan to write the complete step-by-step operating procedure covering: system checks, pump-down sequence, gas introduction, plasma ignition, deposition, shutdown, and emergency stops. Include exact pressure set-points, voltage ramp recommendations, and gauge switching sequence once the Penning interlock threshold is known.]_

***

### Startup / Shutdown Checklists

These checklists are derived from the safety notes and are intended to be printed and kept next to the machine.

#### Safe Startup Sequence (high-level)

1. Visual inspection: no obvious damage, all cables secure, chamber clean and empty of tools.
2. Verify all valves in correct initial state.
3. Start rotary vane pump.
4. When Pirani indicates sufficiently low pressure, start turbo pump.
5. Wait for base pressure (Penning may be turned on only after its interlock threshold is reached).
6. Introduce argon via MFC and stabilize at strike pressure.
7. Apply high voltage (slowly ramp with variac) and ignite plasma.
8. Adjust argon flow / voltage to reach desired sputtering pressure and rate.
9. Begin deposition timer / substrate exposure.

#### Safe Shutdown Sequence (high-level)

1. Reduce / remove high voltage.
2. Stop argon flow.
3. Allow system to pump for a short time.
4. Turn off Penning gauge (if on).
5. Turn off turbo pump (follow manufacturer cool-down / spin-down procedure).
6. When turbo is safe, vent the chamber **only** after turbo and Penning are off.
7. Turn off rotary pump.
8. Isolate power and gas supplies.

**Placeholder**\
_\[Expand into detailed, numbered checklists with exact pressure numbers, switch locations, and interlock status once the system is fully characterized.]_

***

### Automation

**Placeholder**\
_\[Describe any existing or planned automation: pressure interlocks, MFC set-point control, high-voltage interlock, data logging, etc.]_

***

### Software

**Assigned to Aryan in the original notes.**

**Placeholder**\
_\[Aryan to document any control software, scripts, GUI, data-logging tools, or Arduino/PLC code used.]_

***

### Improvements

**Placeholder**\
_\[List of planned or desirable upgrades: better load-lock, water-cooled magnetron, RF capability, thickness monitor, improved interlocks, etc.]_

***

### Troubleshooting & Failure Modes

| Symptom                                  | Possible Cause                                                 | Action                                                                                      |
| ---------------------------------------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Cannot reach base pressure               | Leak (most common), outgassing material, pump issue            | Leak-check with helium or sequential isolation; bake if possible; check O-rings and gaskets |
| Slow pump-down                           | Large virtual leak, dirty chamber, water vapor                 | Thorough cleaning, longer pump, mild bake                                                   |
| Penning gauge arcs / fails               | Powered on at too high pressure                                | Replace head if damaged; enforce strict Pirani interlock                                    |
| Plasma will not strike                   | Pressure too high/low, voltage too low, gas not flowing, short | Check gauges, MFC, variac setting, wiring                                                   |
| Unstable plasma / arcing                 | Contaminated target, poor grounding, water vapor               | Clean target, verify ground, improve base pressure                                          |
| High voltage shock / unexpected behavior | Poor grounding, capacitor not discharged                       | Immediate power-off, re-verify grounding and discharge procedures                           |

**Placeholder**\
_\[Expand with photos of common failure signatures and more detailed diagnostic trees.]_

***

### Glossary

| Term          | Meaning                                                          |
| ------------- | ---------------------------------------------------------------- |
| KF / NW       | Klein Flange / Quick Flange — clamp-style vacuum flange          |
| ISO-K / ISO-F | ISO clamp / bolted flanges                                       |
| CF            | ConFlat — knife-edge metal-seal flange                           |
| VCR           | Vacuum Coupling Radiation — high-integrity metal-gasket fitting  |
| NPT           | National Pipe Thread                                             |
| MFC           | Mass Flow Controller                                             |
| sccm          | Standard cubic centimeters per minute                            |
| Pirani        | Thermal-conductivity vacuum gauge (rough to medium vacuum)       |
| Penning       | Cold-cathode ionization gauge (high vacuum)                      |
| Variac        | Variable autotransformer                                         |
| PEEK          | Polyether ether ketone — high-performance non-conductive polymer |
| GCF           | Gas Conversion Factor (for MFCs)                                 |

***

### India-Specific Sourcing Notes

Several components proved difficult or impossible to source locally and required import or custom machining:

* NPT-to-VCR converters
* Certain KF-to-bolt-flange adapters (salvaged from surplus valves; one candidate found in the US)
* Specific MFC models and VCR gaskets
* High-quality Viton O-rings of exact sizes in some cases

**Workarounds used**

* Local appliance repair shops for microwave transformers and diodes.
* Custom machining of adapters.
* Second-hand MFCs via international marketplaces.
* Electroless nickel plating performed locally after careful rust removal.

**Placeholder**\
_\[Expand into a full table of “hard-to-source” items with exact workarounds, vendor contacts (if shareable), and lead times.]_

***

### To-Do / Missing Content

(Retained and organized from original notes)

#### Power Supply

* [ ] Link all related videos
* [ ] Re-check capacitor-discharge wording
* [ ] Photo / link for HV gloves
* [ ] Proper circuit diagram
* [ ] Photos of each subsection + original open setup (including any relevant incident)

#### Vacuum System

* [ ] Turbo-to-chamber geometry diagram
* [ ] Expand on load-lock alternative
* [ ] Verify exhaust-line wording (Aryamman)
* [ ] Verify Viton-on-CF description
* [ ] Photos of KF assembly, O-rings, flange sizes
* [ ] Exact Penning interlock pressure

#### Chamber

* [ ] Weld-location diagrams
* [ ] O-ring groove diagram
* [ ] Viewport assembly photos & steps
* [ ] Salvaged adapter details (Aryamman)
* [ ] Exact part name of US-found adapter

#### Magnetron

* [ ] CMU documentation hyperlink
* [ ] Photos of this build’s magnetron
* [ ] Full source citations

#### Gas Flow

* [ ] Component links
* [ ] Fifer textbook link / confirmation
* [ ] GCF calculation source
* [ ] Full gas-path block diagram with fitting call-outs
* [ ] Swagelok references

#### Other

* [ ] Complete BOM with costs and links
* [ ] Populate Resources with live links
* [ ] SOP (Aryan)
* [ ] Software (Aryan)
* [ ] Automation section
* [ ] Improvements section
* [ ] All photos currently marked TBD
