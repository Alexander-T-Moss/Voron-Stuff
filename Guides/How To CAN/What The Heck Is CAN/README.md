# What The Heck Is CAN?

CAN is short for Controller Area Network, but we just say CAN cause it sounds cooler (and is faster to type). 

CAN - or to be more specific CAN Bus - is a communication standard from the automotive industry initially intended to reduce the wiring in vehicles, saving on the cost of copper in unnecessary additional wires. If you want to look more into the background of CAN then you can go to the wiki page [here](https://en.wikipedia.org/wiki/CAN_bus) or watch [this](https://www.youtube.com/watch?v=FqLDpHsxvf8) video but lets get back onto explaining it in terms of 3D printers.

Data can be sent over just 2 wires with a CAN Bus which is great for 3D printers as we can get down to just 4 wires (V+ / V- / H / L) connecting our toolhead to the main printer electronics allowing us to more easily use a light weight umbilcal style of wiring instead of heavy drag chains which translates to faster printing!



## What Are The Benefits Of CAN

1. Fewer wires going from the toolhead to the printers main electronics
   1. Less money spent on wires
   2. Simpler wiring and makes going umbilcal easier
2. Easier maintence on the toolhead and makes adding additional things to the toolhead easier
3. All the benefits that come with umbilical (like faster printing!)

## What Are The Draw Backs Of CAN

1. Requires a CAN toolhead PCB and possibly CAN Bus Bridge
   1. Additional costs but this is easily offset by the savings from reduced overall wiring
2. Requires more software configuration than conventional printer wiring