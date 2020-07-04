# Turn LED on and off randomly with one button

## Introduction @unplugged

Often, one button can be used to turn on and off lights. How could you do that with code?

![Animation of the initial project.](https://raw.githubusercontent.com/rypsmith/randomonoffsamebutton/master/Animated%20GIF-downsized_large.gif)

In this activity, you will use a variable to act as a toogle to allow one button to both turn on and off a random LED.

## Step 1 - Setup

Start by removing the ``||basic:forever||`` block. Once removed, bring in a ``||input:on button pressed||`` block.

## Step 2 - Make variables

In the ``||variable:Variables||`` section, make 3 variables, called "Toggle", "RandomX", and "RandomY.

## Step 3 - If ... then ... else

To set up one button to do two different things, you need to put an ``||logic:If then else||`` block inside of the the ``||input:on button pressed||`` block.

```blocks
input.onButtonPressed(Button.A, function () {
    if (true) {
    	
    } else {
    	
    }
})
```

## Step 4 - Set-up the Toggle

The ``||variable:toggle||`` variable acts like a switch that can "on" or "off", or in coding language, ``||logic:true||`` or ``||logic:false||``. Bring in a ``||variables:set toggle to...||`` block and put in inside the ``||basic:on start||`` block. Add in a ``||logic:false||`` block to the end of the ``||variables:set toggle to...||`` block. 

```blocks
input.onButtonPressed(Button.A, function () {
    if (true) {
    	
    } else {
    	
    }
})
let toggle = false
```