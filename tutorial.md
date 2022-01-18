# Multiplayer RPS Game Tutorial

## Step 1

First we set some ground variables
Make 3 new variables and call them: hand_set, hand and ready

```blocks
let hand = 0
let hand_set = 0
let ready = 0
ready = 0
```

## Step 2

You set a radio group (can be anything) 
and a main menu screen with "show leds" and add it in the "on start"

```blocks
let hand = 0
let hand_set = 0
let ready = 0
ready = 0

radio.setGroup(10)
basic.showLeds(`
    # . # . #
    . . . . .
    # . # . #
    . . . . .
    # . # . #
    `)
```

## Step 3

Now you take the "on button A pressed" and place it in your editor


```blocks
input.onButtonPressed(Button.A, function () {
    
})
```

## Step 4

Now you take the "If" block and place it in the onButtonAPressed
Then you take the "0 = 0" block and place it in the statement area in the if block
```blocks
input.onButtonPressed(Button.A, function () {
    if (0 == 0) {

    }
})
```

## Step 5

Next you place a ready variable on the left side of the statement
Then you put a sendString from radio inside the if block
and send "ready"
Next you set ready to 1

```blocks
input.onButtonPressed(Button.A, function () {
    if (ready == 0) {
        radio.sendString("ready")
        ready = 1
    }
})
```

## Step 6

Next you put a "onReceivedString" block down
You take an "If" block and put it in the onReceivedString block
Next you take a "0 = 0" block and put it in the "If" block

```blocks
radio.onReceivedString(function (receivedString) {
    if (0 == 0) {
        
        }
```

## Step 7

Then after you've done that you take  the "receivedString" object and place it
on the left side of the statement. Next you take a "" block from text in the
advanced tab and place it on the left side.

```blocks
radio.onReceivedString(function (receivedString) {
    if (receivedString == "") {
        
        }
```

## Step 8

Then you type "ready" in the "", and place another "If" block inside the "If" block

```blocks
radio.onReceivedString(function (receivedString) {
    if (receivedString == "ready") {
        if (0 == 0) {
            
        }
```

## Step 9

Inside the statement you put a ready variable on the left side and a 0 on the right
Then you make a "waiting for answer" type of picture with the "showLeds" block

```blocks
radio.onReceivedString(function (receivedString) {
    if (receivedString == "ready") {
        if (ready == 0) {
            basic.showLeds(`
                . # # # .
                # . . . #
                . . . . #
                . . # # .
                . . # . .
                `)
        }
```

## Step 10

Next you make a new function named "Start"
```blocks
function Start () {
    
}
```

## Step 11

Then you make a countdown for the round to begin
inside the "Start" function

```blocks
function Start () {
    basic.showNumber(3)
    basic.pause(1000)
    basic.showNumber(2)
    basic.pause(1000)
    basic.showNumber(1)
    basic.pause(1000)
    basic.clearScreen()
}
```
## Step 12

You make a new function called "set_hand" and inside you set "hand_set" to 0

```blocks
function set_hand () {
    hand_set = 0
}
```

## Step 13

Next you take a "while do" loop and put it inside the function
The statement is going to be "hand_set = 0"
Then outside the "while do" block you put a "sendString" block,
take a "hand" variable and place it in the "sendString" block

```blocks
function set_hand () {
    hand_set = 0
    while (hand_set == 0) {
        
    }
    radio.sendString(hand)
}
```

## Step 14

Then after you've done that you make a "If" block and click the + button three times
and remove the "else" statement.

```blocks
function set_hand () {
    hand_set = 0
    while (hand_set == 0) {
        if (true) {
            
        } else if () {
            
        } else if () {
            
        }
    }
    radio.sendString(hand)
}
```

## Step 15

Then you take the "isGesture" or any other type of input you want and place
it inside the "If statement".
Do this for all of the "If" blocks

```blocks
function set_hand () {
    hand_set = 0
    while (hand_set == 0) {
        if (input.isGesture(Gesture.TiltLeft)) {

        } else if (input.isGesture(Gesture.TiltRight)) {

        } else if (input.isGesture(Gesture.LogoUp)) {

        }
    }
    radio.sendString(hand)
}
```

## Step 16

Then inside of the "If" blocks put a "showLeds" block and make the "items"
you want to play with. In this case: Rock, paper and scissors
After the "showLeds" on all "If" blocks put a "set hand_set to 1"

```blocks
function set_hand () {
    hand_set = 0
    while (hand_set == 0) {
        if (input.isGesture(Gesture.TiltLeft)) {
            basic.showLeds(`
                . . . . .
                . # # # .
                . # # # .
                . # # # .
                . . . . .
                `)
            hand_set = 1
        } else if (input.isGesture(Gesture.TiltRight)) {
            basic.showLeds(`
                # # . . #
                # # . # .
                . . # . .
                # # . # .
                # # . . #
                `)
            hand_set = 1
        } else if (input.isGesture(Gesture.LogoUp)) {
            basic.showLeds(`
                . # # # .
                . # # # .
                . # # # .
                . # # # .
                . # # # .
                `)
            hand_set = 1
        }
    }
    radio.sendString(hand)
}
```
## Step 17

Then in the first "If" block you put set hand to "0".
Do the same in the second but change the number to "1"
And the same in the third but change it to "2"

```blocks
function set_hand () {
    hand_set = 0
    while (hand_set == 0) {
        if (input.isGesture(Gesture.TiltLeft)) {
            basic.showLeds(`
                . . . . .
                . # # # .
                . # # # .
                . # # # .
                . . . . .
                `)
            hand = 0
            hand_set = 1
        } else if (input.isGesture(Gesture.TiltRight)) {
            basic.showLeds(`
                # # . . #
                # # . # .
                . . # . .
                # # . # .
                # # . . #
                `)
            hand = 1
            hand_set = 1
        } else if (input.isGesture(Gesture.LogoUp)) {
            basic.showLeds(`
                . # # # .
                . # # # .
                . # # # .
                . # # # .
                . # # # .
                `)
            hand = 2
            hand_set = 1
        }
    }
    radio.sendString(hand)
}
```

## Step 18

Then you click the + button on the "If" block inside the "onReceivedString" block
and put a "sendString" block and a "call Start" block
Inside the sendString you type "start-dir".
And you put a "call set_hand" block at the end of the function "Start"

```blocks
function set_hand () {
    hand_set = 0
    while (hand_set == 0) {
        if (input.isGesture(Gesture.TiltLeft)) {
            basic.showLeds(`
                . . . . .
                . # # # .
                . # # # .
                . # # # .
                . . . . .
                `)
            hand = 0
            hand_set = 1
        } else if (input.isGesture(Gesture.TiltRight)) {
            basic.showLeds(`
                # # . . #
                # # . # .
                . . # . .
                # # . # .
                # # . . #
                `)
            hand = 1
            hand_set = 1
        } else if (input.isGesture(Gesture.LogoUp)) {
            basic.showLeds(`
                . # # # .
                . # # # .
                . # # # .
                . # # # .
                . # # # .
                `)
            hand = 2
            hand_set = 1
        }
    }
    radio.sendString(hand)
}

function Start () {
    basic.showNumber(3)
    basic.pause(1000)
    basic.showNumber(2)
    basic.pause(1000)
    basic.showNumber(1)
    basic.pause(1000)
    basic.clearScreen()
    set_hand()
}

radio.onReceivedString(function (receivedString) {
    if (receivedString == "ready") {
        if (ready == 0) {
            basic.showLeds(`
                . # # # .
                # . . . #
                . . . . #
                . . # # .
                . . # . .
                `)
        } else {
            radio.sendString("start-dir")
            Start()
```

## Step 19

Now you go back to the "onReceivedString" block and add one more "If" block

```blocks
radio.onReceivedString(function (receivedString) {
    if (receivedString == "ready") {
        if (ready == 0) {
            basic.showLeds(`
                . # # # .
                # . . . #
                . . . . #
                . . # # .
                . . # . .
                `)
        } else {
            radio.sendString("start-dir")
            Start()
        }
    }
    if (0 == 0) {
        
    }
})

function Start () {
    basic.showNumber(3)
    basic.pause(1000)
    basic.showNumber(2)
    basic.pause(1000)
    basic.showNumber(1)
    basic.pause(1000)
    basic.clearScreen()
    set_hand()
}

function set_hand () {
    hand_set = 0
    while (hand_set == 0) {
        if (input.isGesture(Gesture.TiltLeft)) {
            basic.showLeds(`
                . . . . .
                . # # # .
                . # # # .
                . # # # .
                . . . . .
                `)
            hand = 0
            hand_set = 1
        } else if (input.isGesture(Gesture.TiltRight)) {
            basic.showLeds(`
                # # . . #
                # # . # .
                . . # . .
                # # . # .
                # # . . #
                `)
            hand = 1
            hand_set = 1
        } else if (input.isGesture(Gesture.LogoUp)) {
            basic.showLeds(`
                . # # # .
                . # # # .
                . # # # .
                . # # # .
                . # # # .
                `)
            hand = 2
            hand_set = 1
        }
    }
    radio.sendString(hand)
}
```

## Step 20

First you click on the + button on the "If" block inside the first "If" block 
and in the "else" statement place a "sendString" block that sends "start-dir"
and a "call Start" block. In the second "If" block take the "receivedString" object
and put it on the left side of the statement. On the other side you take a "" block and type in "start-dir"

```blocks
radio.onReceivedString(function (receivedString) {
    if (receivedString == "ready") {
        if (ready == 0) {
            basic.showLeds(`
                . # # # .
                # . . . #
                . . . . #
                . . # # .
                . . # . .
                `)
        } else {
            radio.sendString("start-dir")
            Start()
        }
    }
    if (receivedString == "start-dir") {
        Start()
    }
    if (0 == 0) {
        
    }
})

function Start () {
    basic.showNumber(3)
    basic.pause(1000)
    basic.showNumber(2)
    basic.pause(1000)
    basic.showNumber(1)
    basic.pause(1000)
    basic.clearScreen()
    set_hand()
}

function set_hand () {
    hand_set = 0
    while (hand_set == 0) {
        if (input.isGesture(Gesture.TiltLeft)) {
            basic.showLeds(`
                . . . . .
                . # # # .
                . # # # .
                . # # # .
                . . . . .
                `)
            hand = 0
            hand_set = 1
        } else if (input.isGesture(Gesture.TiltRight)) {
            basic.showLeds(`
                # # . . #
                # # . # .
                . . # . .
                # # . # .
                # # . . #
                `)
            hand = 1
            hand_set = 1
        } else if (input.isGesture(Gesture.LogoUp)) {
            basic.showLeds(`
                . # # # .
                . # # # .
                . # # # .
                . # # # .
                . # # # .
                `)
            hand = 2
            hand_set = 1
        }
    }
    radio.sendString(hand)
}
```

## Step 21

Take a "onReceivedNumber" block from the radio tab and place one "If" block in it
Next you press the + button three times and remove the else statement

```blocks
radio.onReceivedNumber(function(receivedNumber: number) {
    if (true) {
	
} else if (true) {
	
} else if (true) {
	
}

```

## Step 22

First you drag the receivedNumber object in all statements on the left side

In the first "If" block you type "0"
In the second you type "1"
And in the third you type "2"

```blocks
radio.onReceivedNumber(function (receivedNumber) {
    if (receivedNumber == 0) {
    	
    } else if (receivedNumber == 1) {
    	
    } else if (receivedNumber == 2) {
    	
    }
})
```

## Step 23

First you make a new function called "Switch"
Now you put a "showLeds" block and a pause block. Fill the "showLeds" block entirely
After that you put a "call Switch" block in every "if" block. Then you put a rock, paper and scissors
picture in each of them.

```blocks
function Switch () {
    basic.showLeds(`
        # # # # #
        # # # # #
        # # # # #
        # # # # #
        # # # # #
        `)
    basic.pause(100)
}
radio.onReceivedNumber(function (receivedNumber) {
    if (receivedNumber == 0) {
        Switch()
        basic.showLeds(`
            . . . . .
            . # # # .
            . # # # .
            . # # # .
            . . . . .
            `)
    } else if (receivedNumber == 1) {
        Switch()
        basic.showLeds(`
            . # # # .
            . # # # .
            . # # # .
            . # # # .
            . # # # .
            `)
    } else if (receivedNumber == 2) {
        Switch()
        basic.showLeds(`
            # # . . #
            # # . # .
            . . # . .
            # # . # .
            # # . . #
            `)
    }
})

```

## Step 24

That should be everything! Congratulations! Now enjoy your game!
