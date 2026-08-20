# NMOS

## Process Flow:

1. Field oxide growth in furnace (need to see if oxide quality is good by building MOSCAPs reliably)
2. Coat PPR
3. Litho and develop areas for source and drain
4. Bake and harden the PPR so it can survive HF
5. HF etch the oxide down to silicon in source and drain areas, remove photoresist
6. Coat spin on dopant, do the doping process as described, don't etch the field oxide- this gives visibility of S/D regions crucial for future alignment
7. Coat PPR again, align gate mask between source and drain using XY and theta stages(this will easily be done with our current setup), do the litho and development of gate
8. HF Etch oxide underneath gate region again through photoresist mask as before till it reaches the bottom
9. Remove photoresist
10. Grow a thin gate oxide(start \~100nm and play around with this number) - the etch was done so you can have control over regrowth - this thickness has a high impact on device performance
11. Coat resist for a third mask, this is the contacts walla mask- again do the same litho process- etch through to reach the Si on the source and drain for contacts using PPR as a mask
12. Now you have to actually deposit the gate and contacts metal - one option is LOR PPR, and then do the liftoff process while aligning - second option is blanket metal deposition, then etch everything but what you want after doing PPR and litho and using the PPR as a mask for Al etchant

### Sub-Processes

1.  MOSCAPs through shadow mask - they confirm oxide quality


2.  Etching oxide through PPR as a mask - used again and again in the process flow and a hard nut to crack.


3.  Simple Big diodes - Confirm doping capabilities as well as how good the contacts are


4.  Liftoff/metal etch along with lithography- basically be able to make good arbitrary patterns with metal


5.  Building on 4 and 1 - build MOSCAPs at micron scale by combining


6.  Building on 4 and 3 - build diodes at micron scale by combining


7. Just generally each tool owner should do runs with the tool at least every 2 days, so tools are never a bottleneck

#### Some learnings/suggestions

* Contact & Probing Improvements
  * Indium Paste: Good alternative for contacts, though harder to source.
  * Silver Epoxy: A low temperature conductive bridge suitable for larger initial devices to overcome contact issues
* Photoresist Adhesion & HF Oxide Etch Protection
  * HMDS + Dehydration + Bake: A combination of these step might help us solve the problem of HF attacking photoresist
  * Strict Humidity Control: Perform dehydration bakes and spin coating in a low humidity environment
  * Chromium (Cr) Hard Mask: Deposit a thin metal layer to act as the primary HF barrier, which can also help us with the problem of HF attacking photoresist
  * BOE(Buffered Oxide Etch) might be better for SiO2 etching

#### Some important links:

Previous moscap + diode runs : [HackerFab Characterisation - Google Docs](https://docs.google.com/document/d/1XJMAsDky3MLmV7WHJEA6A1dmiy9wwV_OrWoT6nEKNgk/edit?tab=t.0)\
Moscap lab report(from some course?) : [MOSCap Lab Report (18-410/610 S26) - Google Docs](https://docs.google.com/document/d/1vXfvOCq2npE0pBO5wzHDL6-moE2DDtNtiPALTWdSElE/edit?tab=t.0)\
Reference youtube links for process: [https://youtu.be/h6GWikWlAQA?si=-4tnxWmMNuInQbWL](https://youtu.be/h6GWikWlAQA?si=-4tnxWmMNuInQbWL)(small devices)\
[https://youtu.be/s1MCi7FliVY?si=qV3K9AzkhmW9XfwS](https://youtu.be/s1MCi7FliVY?si=qV3K9AzkhmW9XfwS)(big devices)

RCA Cleaning: [https://youtu.be/bS4VtjRc3og?si=hjJ5zUZQisqlUsgI](https://youtu.be/bS4VtjRc3og?si=hjJ5zUZQisqlUsgI)\
[https://youtu.be/wL10iqP2xI8?si=rpe0rnTaM42b8SS-](https://youtu.be/wL10iqP2xI8?si=rpe0rnTaM42b8SS-)<br>
