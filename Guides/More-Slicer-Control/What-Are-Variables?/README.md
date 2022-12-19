## What Are Variables?

A variable is a piece of data that can have a value assigned to it. There are different types of data which a variable can be, so bellow you'll find all the relavent types you may need to use

| Data Type | Shorthand  | Example's                     | Brief Description            |
| --------- | ---------- | ----------------------------- | ---------------------------- |
| Integer   | int        | 1234 / -42 / 1 / 5662341      | Any whole number             |
| Float     | f/float    | 0.1453 / 123.456 / -123.00    | Any decimal number           |
| String    | str/string | "This is a string!" / "Yoooo" | Any collection of characters |
| Boolean   | bool       | True / False                  | Either True (1) or False (0) |

It's important to know about data types so when you make a variable, you don't store the integer 54 (for example) as the string "54" which would make it behave differently to how you'd expect!

## How Do I Make Variables In SuperSlicer?

It's super easy, no really it is! Under each section in SuperSlicer (`Print Settings`/`Filament Settings`/`Printer Settings`) you will find a `Notes` section. In there you'll find a text field called `Custom Variables`. Here is where you will make your variables (see photo below if needed)

![Screenshot 2022-12-17 at 16.57.32](Voron-Stuff/blob/main/Guides/More-Slicer-Control/What-Are-Variables?/Images/Screenshot%202022-12-17%20at%2016.57.41.png)

The format for defining a variable can be broken down into 3 sections: `VariableName`/`Operator`/`DataBeingAssigned` (e.g. *Variable="Thing"*). So as you can see in the screenshot above, I have two variables defined which I can call elsewhere in SuperSlicer, which I'll get onto in the next section, so I can change my pressure advance depending on wether the printer is printing infill or perimeters.

SuperSlicer is pretty smart, meaning you shouldn't have to define the data type (*int/float/string/bool*) as it will automatically determine this given what is being assigned to the variable. That said it's best practice when defining a string, you put it in speech marks (*"Thing"*) so if you type *"1"* for example, it knows you mean the string 1 and not the numeric integer 1!
