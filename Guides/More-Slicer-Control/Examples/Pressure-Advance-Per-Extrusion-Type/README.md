**Need More Help? Ping me on discord @Alexander Þór 🇬🇧🇮🇸#8355**

------

# Pressure Advance Per Extrusion Type

This customization is based on the [per-extrusion type settings](https://github.com/Alexander-T-Moss/Voron-Stuff/tree/main/Guides/More-Slicer-Control/Per-Extrusion-Type-Settings).

## Setup

Firstly, you will need to define your different pressure advance values in your filament profile of choice, to do this we will use [variables](https://github.com/Alexander-T-Moss/Voron-Stuff/tree/main/Guides/More-Slicer-Control/What-Are-Variables%3F).

![Screenshot]()

In the example above, I have defined 2 pressure advance values with this code:

```cs
; Custom PA Values
Infill_PA = 0.035
Perimeter_PA = 0.03
```

You can define as many variables as you'd like with any name but I find myself only neededing these two, they are also the two variables I'll use in the example bellow.

Now you have defined your pressure advance values, we need to configure SuperSlicer to inject them at the correct points in the G-code file, to do this we'll use the `Between extrusion role change G-code` section in our `Printer Settings`. More info on this can be found [here](https://github.com/Alexander-T-Moss/Voron-Stuff/tree/main/Guides/More-Slicer-Control/Per-Extrusion-Type-Settings).

![Screenshot]()

If you are using the variables above and just have different values, then you can copy and paste this code into the `Between extrusion role change G-code` section, if you are using your own variables, make sure to update the code bellow to call them for the right extrusion type!

```cs
{if extrusion_role=~/InternalPerimeter/}
SET_PRESSURE_ADVANCE ADVANCE={Perimeter_PA}

{elsif extrusion_role=~/ExternalPerimeter/}
SET_PRESSURE_ADVANCE ADVANCE={Perimeter_PA} 

{elsif extrusion_role=~/InternalInfill/}
SET_PRESSURE_ADVANCE ADVANCE={Infill_PA}

{elsif extrusion_role=~/SolidInfill/}
SET_PRESSURE_ADVANCE ADVANCE={Infill_PA}

{elsif extrusion_role=~/TopSolidInfill/}
SET_PRESSURE_ADVANCE ADVANCE={Infill_PA}

{elsif extrusion_role=~/BridgeInfill/}
SET_PRESSURE_ADVANCE ADVANCE={Infill_PA}

{elsif extrusion_role=~/InternalBridgeInfill/}
SET_PRESSURE_ADVANCE ADVANCE={Infill_PA}

{elsif extrusion_role=~/Thin Wall/}
SET_PRESSURE_ADVANCE ADVANCE={Perimeter_PA}

{elsif extrusion_role=~/GapFill/}
SET_PRESSURE_ADVANCE ADVANCE={Perimeter_PA}

{elsif extrusion_role=~/Skirt/}
SET_PRESSURE_ADVANCE ADVANCE={Perimeter_PA}

{endif}
```



## Calibrating Pressure Advance Values

I strongly recommend you use [Ellis's pressure advance calibration tool](https://ellis3dp.com/Print-Tuning-Guide/articles/pressure_linear_advance/pattern_method.html). The only thing that should change when tunining each pressure advance value is the speed. I typically prefer to run a slightly higher infill pressure advance to get nicer top surfaces.