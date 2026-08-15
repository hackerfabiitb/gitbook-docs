---
description: This is the official HackerFab IITB documentation for the thermal evaporator
---

# thermal-evaporator-v1

## The Thermal Evaporator

### Introduction: What is a Thermal Evaporator?

A thermal evaporator is a Physical Vapor Deposition (PVD) system used to deposit extremely thin films of metals (or other materials) onto a substrate. It operates inside a high-vacuum chamber.

The core principle is resistive heating: a very high electrical current is passed through a refractory metal filament (usually shaped like a basket or boat made of Tungsten or Molybdenum). The target material (like Aluminum pellets) is placed inside this filament. As the filament heats up, the metal melts and then evaporates. Because this happens in a high vacuum, the vaporized metal atoms travel in straight lines without colliding with air molecules, eventually condensing as a highly uniform thin film on the cooler substrate positioned above it.

\[PLACEHOLDER: Add a picture of the overall finished Thermal Evaporator setup here]

### Disclaimer

This documentation is provided for educational and informational purposes only. Building and operating a thermal evaporator involves extreme temperatures, high electrical currents, and hazardous materials (metal vapour). By following this guide, you acknowledge that you are doing so at your own risk. The authors and HackerFab IITB are not responsible for any property damage, injury, or loss of life that may occur as a result of attempting this project. Always consult a qualified professional if you are unsure about electrical wiring or high-temperature systems. Please read the safety section carefully before proceeding.

### Specs

* Current Rating: 50 - 60 Amps
* Rotary Pump Pump-down Time (Atm to 1e-3 mbar): \~20 minutes
* Turbo Pump Pump-down Time (1e-3 to 1e-5 mbar): \~30 minutes
* Clearance (Filament to Substrate): 8.5 cm
* Evaporation Duration: 10 - 12 minutes
* Post-Process Cooling Time: 20 - 25 minutes

### Bill of Materials (BOM)

| Item                | Description/Source                               | Cost (INR)   | Type  |
| ------------------- | ------------------------------------------------ | ------------ | ----- |
| Vacuum Chamber      | Upcycled from Sputter v-2 build                  | N/A          | Capex |
| Rotary Pump         | Upcycled from Sputter v-2 build                  | N/A          | Capex |
| Turbo Pump          | Upcycled from Sputter v-2 build                  | N/A          | Capex |
| Pirani Gauge        | Upcycled from Sputter v-2 build                  | N/A          | Capex |
| Penning Gauge       | Upcycled from Sputter v-2 build                  | N/A          | Capex |
| Copper Feedthroughs | Custom made at RD Brothers (Khairani Road)       | ₹ 2,000      | Capex |
| Teflon Washers      | Machined at RD Brothers (Khairani Road)          | ₹ 1,000      | Capex |
| Gaskets             | Viton sheet machined at RD Brothers              | _\[Cost?]_   | Capex |
| Substrate Stand     | Custom machined from Stainless Steel (SS)        | _\[Cost?]_   | Capex |
| Power Supply        | Welding PSU (220V AC mains, 220A max output)     | _\[Cost?]_   | Capex |
| Electrical Gloves   | Electrically insulated; rated for at least 1000V | _\[Cost?]_   | Capex |
| Tungsten Filament   | Basket style; KMV Vacuum Technology, Bangalore   | \~₹ 900 / ea | Opex  |
| Target Metal        | e.g., Aluminum pellets (\~100 grams)             | \~₹ 2,500    | Opex  |

_\[PLACEHOLDER: Add exact model, bill link, and cost of Welding Power Supply]_ _\[PLACEHOLDER: Add costs for the gaskets and substrate stand if known]_

### The Build

Note: For the primary vacuum chamber build, please refer to the Sputter v-2 documentation. The thermal evaporator uses the same chamber with modifications to accommodate high-current electrical feedthroughs.

The feedthrough design is based on the concepts shown in [this reference video](https://youtu.be/97716PkbX2M?si=dOTJ5MCQwBpCHEew).

Step-by-Step Assembly:

1. Feedthrough Preparation: Design and machine the copper feedthroughs. You also need to manufacture custom Teflon washers (for electrical isolation) and Viton gaskets (for vacuum sealing).
2. Chamber Modification: Drill two precisely spaced holes into the bottom plate of the sputter chamber to house the feedthroughs.
3. Feedthrough Installation: Install the copper feedthroughs into the bottom plate, ensuring the Viton gaskets and Teflon washers are placed correctly to maintain a tight vacuum seal and prevent electrical shorting to the steel chamber.
   * \[PLACEHOLDER: Add a picture/diagram showing exactly where the Teflon washers and Viton gaskets sit relative to the chamber wall and feedthrough]
4. Power Connection: Connect the high-current output lines of the welding power supply securely to the external ends of the copper feedthroughs.
   * \[PLACEHOLDER: Add a picture showing the welding power supply connected to the feedthroughs]
5. Filament Installation: Inside the chamber, bridge the two copper feedthroughs using the Tungsten basket filament. Ensure the connections are tight, but do not put mechanical stress on the filament, as Tungsten is brittle.
   * \[PLACEHOLDER: Add a close-up picture of the Tungsten filament connected to the feedthroughs]
6. Load Target Material: Place the metal evaporation pellets (e.g., Al) directly inside the Tungsten filament basket.
   * \[PLACEHOLDER: Add a picture of the pellets loaded in the basket]

### Standard Operating Procedure (SOP)

#### Phase 1: Chamber Preparation & Loading

1. Open Chamber: Take the top plate off the chamber by unscrewing the diagonally opposite screws.
2. Remove Internals: Carefully take the SS substrate stand out of the chamber.
3. Cleaning: Clean the entire internal chamber and all components that go inside (especially the substrate stand) using Acetone, followed by IPA. _Do this while wearing nitrile gloves to avoid transferring oils from your skin._
4. Install Filament: Connect the Tungsten filament across the feedthroughs. Caution: Do not apply excessive mechanical stress to the filament, or it will snap.
5. Load Pellets: Place your metal pellets inside the Tungsten filament.
6. Place Substrate: Put the SS stand back into the chamber. Place your substrate onto the stand. Double-check that the substrate is positioned perfectly over the hole in the stand, sitting at the correct height (8.5 cm) directly above the Tungsten basket. You can put a glass slide next to the silicon wafer if depositing on silicon to observe whether the deposition has started.
7. Seal Chamber: Place the top plate back on and begin screwing it in.
8. Connect Gauges: Connect both the Pirani gauge and the Penning gauge to their respective ports on the top plate.

#### Phase 2: Pump Down

9. Start Pirani: Turn on the Pirani gauge. The orange light will turn on, and it will read `999` (indicating atmospheric pressure).
10. Roughing Vacuum: Turn on the rotary pump. As the pump runs, firmly tighten the top plate screws to compress the O-ring and create a proper vacuum seal. The orange light on the gauge will turn off as pressure drops.
11. Open Turbo Valve: Wait for the rotary pump to bring the pressure down to 70-80 mbar. Once there, open the turbo valve to continue dropping the pressure.
    * \[PLACEHOLDER: Add a picture of the Pirani gauge reading 70-80 mbar]
    * \[PLACEHOLDER: Add a picture showing which valve is the turbo valve and how to open it]
12. Wait for High Vacuum Threshold: Wait approximately 20 minutes for the pressure to reach 1e-3 mbar.
13. Start High Vacuum: Turn on the Penning gauge, then turn on the turbo pump.
14. Wait for Target Vacuum: Wait roughly 30 minutes for the pressure to reach 1e-5 mbar.

#### Phase 3: Evaporation Process

15. Power Up (Wear 1000V rated gloves!): Turn on the welding power supply.
16. Ramp Current: Slowly ramp up the current in increments of 10 Amps at a time. Wait 30 seconds between each step to avoid thermal shock, until you reach a final current of 55 Amps.
17. Evaporate: Maintain 55 Amps for 10-12 minutes to complete the deposition process. We have observed that it takes around 6-7 minutes for the evaporation to start, probably because of the time taken to heat the tungsten and start evaporation.
18. Monitor Temperature: Periodically check the external temperature of the copper feedthroughs using a thermal gun. (Copper usually reaches only about 40°C at 55A; it is safe up to 200°C).
    * \[PLACEHOLDER: Add a picture demonstrating measuring the feedthrough temperature with the thermal gun]

#### Phase 4: Shutdown & Venting

19. Ramp Down (Wear 1000V rated gloves!): Gradually step the current down to 0 Amps, then turn off the power supply.
20. Cooling Period: Wait 25 minutes for the Tungsten filament to cool down. _Crucial:_ If a hot Tungsten filament is exposed to atmospheric oxygen, it will immediately oxidize and burn out.
21. Power Down Gauges & Turbo: Turn off the Penning gauge. Turn off the turbo pump by first turning off the switch from the front and then wait for the lights on it for the speed to turn off. This takes 15 minutes. The pressure will gently rise to about 1e-4 or 1e-3 mbar.
22. Turn off turbo pump from the back.&#x20;
23. Power Down Rotary: Turn off the rotary pump. Wait roughly 20 minutes for the system to naturally vent back to atmospheric pressure.
24. Final Shutdown: Turn off the Pirani gauge and carefully remove both gauges and the MFC from the top plate.&#x20;
25. Unload: Open the top plate and take out your coated substrate!

### Safety Guidelines

As students, we tend to disregard the matter of safety under the impression _"kya hi ho jaayega?"_. However, the thermal evaporator is not a toy. Bypassing safety protocols here can result in severe injury or loss of life. We at HackerFab IITB always follow strict protocol, and you must do the same.

#### 1. Electrical Safety

The evaporator uses a welding power supply to drive 55 Amps of current through an exposed metal chassis. A simple mistake like touching the live copper feedthroughs can be fatal.

* Grounding: The chamber is made of stainless steel/mild steel and will carry leaking current. The entire enclosure must be securely grounded. Always use a multimeter to check for continuity between the chamber body and earth ground before starting the system.
* PPE (Gloves): You must wear electrically insulated gloves rated for at least 1000V whenever you are interacting with the power supply (turning it on, ramping it, or turning it off).

#### 2. High Temperature & Fire Hazards

The filament inside reaches temperatures capable of vaporizing metal, making the surrounding setup a severe fire hazard.

* Workspace Surface: Keep the evaporator on a non-combustible surface (like a concrete table, thick ceramic tiles, or a steel table).
* Clearance: Ensure there are no flammable materials, chemicals, solvents (keep the cleaning IPA/Acetone far away!), or papers within at least a 1-meter radius of the machine.
* Fire Extinguisher: Always keep a suitable fire extinguisher immediately accessible.
* Thermal Discipline (Cooling Time): Always respect the 25-minute cooling rule after evaporation before venting the chamber. Opening it while the filament is hot will destroy the filament and create a spontaneous fire/burn hazard.

#### 3. Material Handling & Chemical Hazards

* Consult the MSDS: Always check the Material Safety Data Sheet (MSDS) of the target metal before evaporating it. You might think you are playing with a harmless material, only to find out its vapour or oxide form is a toxic carcinogen!
* Hygiene: Wear nitrile gloves during the entire cleaning and loading process to avoid skin exposure to solvents, metal residues, and to prevent contaminating the vacuum chamber with organic oils from your hands.

### Thermal Evaporator V2: Planned Improvements

While the current setup is functional, the following improvements are planned for the next iteration of the evaporator to increase safety, reliability, and ease of use:

1. Dedicated Chamber: The current evaporator shares a chamber with the Sputter setup. V2 will feature a completely separate, dedicated vacuum chamber. This will allow both machines to be operated independently and simultaneously, increasing lab throughput and preventing cross-contamination between processes.
2. Turbo Pump Isolation Valve (Baffle/Flap): A high-vacuum gate valve or baffle will be installed between the turbo pump and the main chamber. This will allow the turbo pump to be closed off once the target vacuum is reached, preventing evaporated metal vapors from entering the pump, condensing on the rapidly spinning blades, and causing mechanical failure or unbalancing.
3. Thickness Monitor: Integrating a Quartz Crystal Microbalance (QCM) inside the chamber to measure the thickness of the deposited film in real-time, allowing for precise control over the final coating thickness.

{% embed url="https://www.youtube.com/watch?v=97716PkbX2M" %}
