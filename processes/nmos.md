---
description: 'Process flow:'
---

# NMOS

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
