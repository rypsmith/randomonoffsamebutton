# Turn LED on and off randomly with one button

## Introduction @unplugged

Often, one button can be used to turn on and off lights. How could you do that with code?

![Animation of the initial project.](https://raw.githubusercontent.com/rypsmith/randomonoffsamebutton/master/Animated%20GIF-downsized_large.gif)

In this activity, you will use a variable to act as a toogle to allow one button to both turn on and off a random LED.

## Step 1 - Setup

Start by removing the ``||basic:forever||`` block. Once removed, bring in a ``||input:on button pressed||`` block.

## Step 2 - Make variables

In the ``||variable:Variables||`` section, make 3 variables, called "toggle", "randomX", and "randomY.

## Step 3 - If ... then ... else

To set up one button to do two different things, you need to put an ``||logic:if then else||`` block inside of the the ``||input:on button pressed||`` block.

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
toggle = false
```

## Step 5 - Conditional Statement Set-up

A conditional statement - like an "if" statement, need some conditions to be true or false, in order to work. First we check to make sure ``||variable:toggle||`` is false. Get a ``||logic: = (equals)||`` block and place it inside the ``||logic:if then||`` part of the block.

```blocks
input.onButtonPressed(Button.A, function () {
    if (0 == 0) {
    	
    } else {
    	
    }
})
let toggle = false
toggle = false
```

## Step 6 - Make the conditions

Now place a ``||variable:toggle||`` block in the first value (currently a zero) in the "equals" condition, and place a ``||logic:false||`` block in the second value for the condional statement.

```blocks
input.onButtonPressed(Button.A, function () {
    if (toggle == false) {
    	
    } else {
    	
    }
})
let toggle = false
toggle = false
```

## Step 7 - Disable the button

Now that the button has been pressed once, we first want to disable it from being activated again by the user, get a ``||variables:set toggle to...||`` block and insert it in the first part of the "if/else" statement. Add a ``||logic:true||`` block in the ``||variables:set toggle to...||`` block.

```blocks
input.onButtonPressed(Button.A, function () {
    if (toggle == false) {
        toggle = true
    } else {
    	
    }
})
let toggle = false
toggle = false
```

## Step 8 - Pick some random numbers

Bring in a ``||variables:set randomX to...||`` block and a ``||variables:set randomY to...||`` block and place them underneith the ``||variables:set toggle to...||`` block. Put a ``||math:pick random||`` in each.

```blocks
input.onButtonPressed(Button.A, function () {
    if (toggle == false) {
        toggle = true
        randomX = randint(0, 10)
        randomY = randint(0, 10)
    } else {
    	
    }
})
let randomY = 0
let randomX = 0
let toggle = false
toggle = false
```

## Step 9 - Set the range for the random numbers.

Remember that the range for the LED pixels is from 0 to 4, so adjust both ``||math:pick random||`` blocks so that they are picking between 0 and 4.

```blocks
input.onButtonPressed(Button.A, function () {
    if (toggle == false) {
        toggle = true
        randomX = randint(0, 4)
        randomY = randint(0, 4)
    } else {
    	
    }
})
let randomY = 0
let randomX = 0
let toggle = false
toggle = false
```

## Step 10 - LED ON!

Now use these random numbers you've made and turn on the LED that corresponds! Bring in a ``||led:plot x y||`` block. Place ``||variables:randomX||`` in the x value and ``||variables:randomY||`` in the y value. Once done, press the A button to make sure that one LED is turned on!

```blocks
input.onButtonPressed(Button.A, function () {
    if (toggle == false) {
        toggle = true
        randomX = randint(0, 4)
        randomY = randint(0, 4)
        led.plot(randomX, randomY)
    } else {
    	
    }
})
let randomY = 0
let randomX = 0
let toggle = false
toggle = false
```

## Step 11 - Get toggle set-up for 'off'

Now that "on" is working for the one button, now "off" needs to work with the same button. First you need to adjust the ``||variables:set toggle to...||`` by setting it to ``||logic:false||``. Do this inside the "else" area of the ``||logic:if then else||`` block.

```blocks
input.onButtonPressed(Button.A, function () {
    if (toggle == false) {
        toggle = true
        randomX = randint(0, 4)
        randomY = randint(0, 4)
        led.plot(randomX, randomY)
    } else {
        toggle = false
    }
})
let randomY = 0
let randomX = 0
let toggle = false
toggle = false
```

## Step 12 - Turn the LED off!

Finally the last step! Bring in a ``||led:unplot x y||``. Again, place ``||variables:randomX||`` in the x value and ``||variables:randomY||`` in the y value. Once done, press the A button to make sure that same one LED is turned off!

```blocks
input.onButtonPressed(Button.A, function () {
    if (toggle == false) {
        toggle = true
        randomX = randint(0, 4)
        randomY = randint(0, 4)
        led.plot(randomX, randomY)
    } else {
        toggle = false
        led.unplot(randomX, randomY)
    }
})
let randomY = 0
let randomX = 0
let toggle = false
toggle = false
```