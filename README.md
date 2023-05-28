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

## 3. Basics - Arithmetics & Variables
First of all we need to see diffrent types of expressions. In krypton we have three types:

- Math expressions

Standard math. Nothing special.

- Text expressions

Normal text with variable support. Can't use any arithmetic operations.

- Universal expression

Expression where first character defines type. "$" means it is being parsed as text expression, "\*" is no parsing, and no symbol means traditional math parser.


We've also included special constans that can be used in math and text expressions. 

```
PLAYER_X
PLAYER_Y
PLAYER_Z
PLAYER_MOTION_X
PLAYER_MOTION_Y
PLAYER_MOTION_Z
PLAYER_HOTBAR_SLOT (incremeneted starting from 0)
PLAYER_EYEHEIGHT
PLAYER_ONGROUND (0 or 1)
PLAYER_SNEAKING (0 or 1)
```

__***FOR VARIALES, I WILL POST A FRAGMENT OF OLD DOCUMENTATION***__

**3. Variables**
To set variable use one of the two commands
```ts
SETVAL:
[Variable Name]:[Value as raw expression]
RSETVAL:
[Variable Name]:[Value as universal expression]
```
Here are usage examples:
```ts
SETVAL:
test:PLAYER_X 
```
In this example variable test will be "PLAYER_X"
```ts
RSETVAL:
test:PLAYER_X
```
In this example variable test will be equals to whatever the player x position is. For example if player x is 5, the variable will be 5

To reference variables in Expressions use following syntax:
```ts
VAR([variable name])
```
For example following code:
```ts
SETVAL:
test:-1
RSETVAL:
test:VAR(test)+1
```
Will set variable "test" to -1 then make it 0.
Note that operations like that:
```ts
SETVAL:
test:Hello
RSETVAL:
test:VAR(test)+1
```
Won't be executed and will terminate the program as the expression (Hello+1) can't be parsed properly. It would work properly if set like that:
```ts
SETVAL:
test:Hello
RSETVAL:
test:$VAR(test)1
```
With above example variable test will become "Hello1'

**4. Commands**

Here are the commands:
