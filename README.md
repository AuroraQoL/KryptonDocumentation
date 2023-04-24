# Krypton Documentation

> Following docs are valid mainly for regular Krypton version 1 rev 3. For understanding the free version please refer to the source code

## 1. Understanding the syntax
Krypton uses very basic and easy-to learn syntax
```ts
(INSTRUCTION): // case-insensivite since krypton 1.2
[EXPRESSIONS]
```
This is what we call the **DoubleExecs** syntax.
It is made of two pieces, and is really easy to adap to. For example:
```ts
SWAPHOTBAR:
3
```
Changes hotbar to the 4th slot (because in decimal system 0 is the first index). Of course you can put diffent stuff, use mixed case and more. Lets take look at that:
```ts
swapHotbar:
30-(3^3) // this expression equals to 3
```
This code is equavilent to the one we shown before. More on this will be explained in later tutorial stages.

## 2. How-to?
You put krypton scripts in **.minecraft/krypton** folder.
They are executed automatically upon the **executor** is run. More 'bout executors in later tutorial.

Krypton scripts should follow a set of naming rules
```
FILENAME -> snake case ( krypton_script.ks )
VARIABLES -> upper snake case ( MY_VARIABLE )
```

## 3. Basics - Executors
To define an **executor** please use the standard DoubleExec syntax with exception on the chest trigger.

Here all the triggers:


**CHAT MESSAGE TRIGGER**
```
ONCHAT:
(Text)
```
The following triggers when message recieved by user contains specified Text.
> **💡 TIP:** This can be used for executing script from script. More in this in the "Practical uses and examples" section


**CHEST OPEN TRIGGER**
```
ONCHEST
```
Triggers on chest open. Note that this trigger is not like a regular expression!


**CHAT MESSAGE TRIGGER**
```
ONCHAT:
(Text)
```
The following triggers when message recieved by user contains specified Text.
> **💡 TIP:** This can be used for executing script from script. More in this in the "Practical uses and examples" section


**KEYBOARD TRIGGER**
```
ONKEY:
(Keycode)
```
The following triggers when the following key is clicked.
To view keycodes [click here](https://minecraft.fandom.com/wiki/Key_codes#Before_1.13)



