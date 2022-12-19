**Need More Help? Ping me on discord @Alexander Þór 🇬🇧🇮🇸#8355**

------

# Per-Extrusion Type Settings

This is probably one of the **most powerful** things you can setup in SuperSlicer that will be the basis of 90% of any advanced customizations you want to make to your print settings, and it's really easy to set up!

We utilises SuperSlicers `Between extrusion role change G-code` section under `Custom G-Code` in `Printer Settings` to enable this extra level of settings. The way this section works is pretty simple, when superslicer is slicing and their is a change in the `extrusion role` it will add some G-code we have defined into the file at this point, so we can use some simple *if statments* to make it add G-code only when the next `extrusion role` is what we want to modify. 

![Screenshot]()

## Setting It Up

Copy the code below into the `Between extrusion role change G-code` section:
```
{if extrusion_role=~/InternalPerimeter/}
; Your G-code/Macros to be run before printing Internal Perimeters

{elsif extrusion_role=~/ExternalPerimeter/}
; Your G-code/Macros to be run before printing External Perimeters

{elsif extrusion_role=~/InternalInfill/}
; Your G-code/Macros to be run before printing Internal Infill

{elsif extrusion_role=~/SolidInfill/}
; Your G-code/Macros to be run before printing Solid Infill

{elsif extrusion_role=~/TopSolidInfill/}
; Your G-code/Macros to be run before printing Top Solid Infill

{elsif extrusion_role=~/BridgeInfill/}
; Your G-code/Macros to be run before printing Bridge Infill

{elsif extrusion_role=~/InternalBridgeInfill/}
; Your G-code/Macros to be run before printing Internal Bridge Infill

{elsif extrusion_role=~/Thin Wall/}
; Your G-code/Macros to be run before printing Thin Wall

{elsif extrusion_role=~/GapFill/}
; Your G-code/Macros to be run before printing Gap Fill

{elsif extrusion_role=~/Skirt/}
; Your G-code/Macros to be run before printing Skirts

{endif}
```

Then it's as simple as adding your G-code and Macros where indicated in the code and you're away!

**Note:** If, for example, you update the pressure advance when there is `TopSolidInfill` it will not revert back to the original pressure advance value after printing the `TopSolidInfill` so make sure to define a pressure advance value for each `extrusion_role`!