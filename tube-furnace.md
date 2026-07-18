---
description: This is the official HackerFab IITB documentation for the tube furnace.
---

# tube-furnace

## The Tube Furnace

A tube furnace is a special piece of equipment widely used in many labarotaries to carry out various chemical reactions in a controlled manner. In the case of semiconductors, tube furnaces are used mainly for carrying out the oxidation of Silicon or n-type doping.

$$
\Large Si + O_2 \xrightarrow{1100°C} SiO_2
$$

The tube furnace we have built at HackerFab IITB is currently designed for oxidation only, however we plan to modify it and implement phosphurus doping soon. This is what it looks like!

<figure><img src=".gitbook/assets/84B24CF3-BC6E-421A-8579-179F10D9CB89_1_102_a.jpeg" alt=""><figcaption></figcaption></figure>

## Specs

Standard Operating Temperature : 1100±5°C

Heating Zones : Single Zone Configuration&#x20;

Tube Dimensions :&#x20;

Tube Material : Quartz

Temperature Controller : Multispan UTC-4202G+

## Bill of Materials&#x20;

<table><thead><tr><th width="153.6640625">Material</th><th>Purpose</th><th>Quantity</th><th>Cost</th><th width="149">Net Cost (INR)</th></tr></thead><tbody><tr><td>Quartz Tube (67mm dia, 800mm)</td><td>Tube</td><td>1</td><td>Vendor will give a Quotation</td><td>4000</td></tr><tr><td>Kanthal A1 14 SWG</td><td>Heating Element</td><td>1 kg</td><td>Depends on vendor (INR 3-5k)</td><td>4703.39 </td></tr><tr><td>Kanthal A1 20 SWG</td><td>A "brace" for the heating element</td><td>100 g</td><td>Depends on the vendor</td><td>300</td></tr><tr><td>Whytheat A</td><td>Refractory Cement</td><td>25 kg</td><td>INR 168/kg. The rate for Whytheat is pretty standard</td><td>4200</td></tr><tr><td>Inner PVC Pipe (75mm dia, 1m length)</td><td>To create the cement mold</td><td>1</td><td>Depends on vendor, but PVC pipes are in every hardware store and they are pretty cheap.</td><td>300</td></tr><tr><td>Outer PVC Pipe (160 mm dia, 1m length)</td><td>To create cement mold</td><td>1</td><td>Depends on vendor</td><td>500</td></tr><tr><td>Steel Rod of diameter 7mm and length 60 cm</td><td>Used to coil the kanthal </td><td>1</td><td>Depends on the steel shop. They will probably just cut a bigger rod</td><td>100</td></tr><tr><td>Ceramic Wool of density 96g/cc</td><td>Used as insulation around the refractory cement cast</td><td>10 kgs</td><td>110/kg, again the rate for ceramic wool is pretty standard.</td><td>1100</td></tr><tr><td>MS Sheets (3 by 4 feet)</td><td>Will be made into the enclosure </td><td>4 sheets (~30 kgs)</td><td>Go into the steel market and buy it yourself. The cheapest rate I found it at in Mumbai was 90/kg. There were some vendors trying to sell it to me at 200/kg as well.</td><td>2700</td></tr><tr><td>Steel angles (100cm)</td><td>To provide mechanical support and strengthen the steel enclosure</td><td>2</td><td>Again, depends on the vendor. They are pretty cheap and you should be able to get them under 200 rupees.</td><td>400</td></tr><tr><td>Screws</td><td>To make one face of the steel enclosure removable</td><td>20</td><td>1 rupee per screw </td><td>20</td></tr><tr><td>Temperature Controller (Multispan UTC-4202G+)</td><td>For PID Temperature control</td><td>1</td><td>Buy the temperature controller as per budget. Read the section on the temperature controller to get to know more</td><td>3300</td></tr><tr><td>Solid State Relay (SSR) 40 Amps</td><td>For electrical isolation, and helps the temperature controller do its job using PWM</td><td>1</td><td>As per MRP. This will be available in any electronics store</td><td>250</td></tr><tr><td>Aluminium Heat Sink</td><td>To help regulate the temperature of the SSR</td><td>1</td><td>As per MRP. This may take some time to find.</td><td>200</td></tr><tr><td>Thermal Paste</td><td>Goes between the heat sink and the SSR</td><td>1</td><td>As per MRP. You'll find this in any laptop repair shop</td><td>100</td></tr><tr><td>Bakelite Connector 30 Amps (6-Way open connection)</td><td>Connects Mains voltage, SSR and heating element. This is where all the electronic components meet.</td><td>1</td><td>As per MRP. This may take some time to find.</td><td>30</td></tr><tr><td>Mains Switch (Single Pole MCB, 25 Amps)</td><td>Turn this on to let power from your outlet into your circuit</td><td>1</td><td>As per MRP. You'll find this in your normal electronics store</td><td>300</td></tr><tr><td>Heating Switch (Single Pole MCB, 2 Amps Rocker type)</td><td>Turn this on to let power from your circuit into your heating element</td><td>1</td><td>As per MRP. </td><td>300</td></tr><tr><td>LED Light (Big one)</td><td>Indicates whether the tube furnace is on or off</td><td>2</td><td>As per MRP. </td><td>40</td></tr><tr><td>K type MI thermocouple (Mineral insulated)</td><td>To measure the temperature. The thermocouple should be of appropriate dimensions and should be mineral insulated</td><td>1</td><td>Vendor will give you a quotation</td><td>1950</td></tr><tr><td>Internal wiring (2.5 sqmm)</td><td>To connect the high current parts of the circuit</td><td>1m</td><td>35-50/meter</td><td>50</td></tr><tr><td>Internal wiring (1 sqmm)</td><td>Normal electrical wires to connect everything</td><td>2m</td><td>20-30/meter</td><td>60</td></tr><tr><td>Metal Box</td><td>To keep all the electrical components</td><td>1</td><td>You can find some scrap box or make this yourself</td><td>0</td></tr><tr><td>Quartz Boat with hook</td><td>To keep the silicon wafer</td><td>1</td><td>Vendor will give a quotation</td><td>100</td></tr><tr><td>Push-Pull Quartz rod (Length 1m)</td><td>To push and pull the quartz boat in and out of the tube furnace</td><td>1</td><td>Vendor will give a quotation</td><td>600</td></tr><tr><td></td><td></td><td></td><td></td><td><strong>25,603.39</strong></td></tr></tbody></table>

##
