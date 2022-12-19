# How Do I Use Variables?

You can replace where you'd normally put values into something like a command with a variable, that way, when you change the variable, everywhere that variable is will be updated at the same time allowing us to do some pretty cool things! I'll use the example of setting pressure advance values for different extrusion types and filaments to explain this better!

## Utillising Variables

One way you could use variables is to define multiple pressure advance values per-filament profile for different extrusion types. This is useful when you're printing different extrusion types (infill/perimeters) at greatly different speeds and need slightly different pressure advance values for each! 

**Note:** To do this, you need to know how to use SuperSlicers `Between extrusion role change G-code` section which I cover in more detail ***here***. I'll be glossing over this part in this guide as it's not entirely relevant!

First of all, you need to make the variables to store your pressure advance values. So head over to your `Filament Setting` in SuperSlicer and go to the `Notes` section of the filament profile you wish to set custom pressure advance variables for. In the `Custom variables` text field, you can define as many different pressure advance values as you'd like but I personally just set one for infill and one for perimeters/anything else. 

You can name these variables anything you like but it's best practice to name it related to what data is being stored and the name **cannot contain spaces**. When it comes to assigning a value to the variable, you use the = operator and providing the value you put after the = sign contains a decimal point, SuperSlicer will automatically interpret the variable as a float (*decimal number*).

![Screenshot]()

Now that we've defined our variables, we can use them in the `Between extrusion role change G-code` section in SuperSlicer.

![ScreenShot](https://github.com/Alexander-T-Moss/Voron-Stuff/blob/main/Guides/More-Slicer-Control/How-Do-I-Use-Variables%3F/Images/Screenshot%202022-12-17%20at%2016.57.32.png)

Looking at the `SET_PRESSURE_ADVANCE ADVANCE={Perimeter_PA}`lines in the screenshot above, there are a few key points we can notice. We have used our `Perimeter_PA` variable as the value we are passing through to klipper but more importantly it's inside curly brackets. This is so SuperSlicer know's we want to put the variable `Perimeter_PA` their and not the string "Perimeter_PA"

And that's basically it, now you know all the basics for how to use variables in SuperSlicer!

