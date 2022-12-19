# How Do I Use Variables?

You can replace where you'd normally put values into something like a command with a variable, that way, when you change the variable, everywhere that variable is will be updated at the same time allowing us to do some pretty cool things! I'll use the example of setting pressure advance values for different extrusion types and filaments to explain this better!

## Utillising Variables

One way you could use variables is to define multiple pressure advance values per-filament profile for different extrusion types. This is useful when you're printing different extrusion types (infill/perimeters) at greatly differnet speeds and need slightly different pressure advance values for each! 

**Note:** To do this, you need to know how to use SuperSlicers `Between extrusion role change G-code` section which I cover in more detail ***here***. I'll be glossing over this part in this guide as it's not entirely relevant

