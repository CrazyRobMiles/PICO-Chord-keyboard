# Case Design

The case is created by a Python program that can be used to generate cases containing a large number of different elements. The program is called **BoxMacro.FCMacro** and runs inside the FreeCAD design tool which you can download from [here](https://www.freecadweb.org/downloads.php).

Each element in an enclosure is represented by one or more classes which are then automatically placed inside the base or the lid of the case. It is a bit of a pain to work with, I call it "3,000 lines of technical debt" but it does the job. 
## Moving keys up and down
Line 3181 in the current version of BoxMacro.
```
# adjust these offsets to move the keys up and down
    sw1=KeySwitchHole("Keyswitch1",xMargin=5,yMargin=10,slotYOffset=0)
    sw2=KeySwitchHole("Keyswitch2",xMargin=1,yMargin=2,slotYOffset=18)
    sw3=KeySwitchHole("Keyswitch3",xMargin=1,yMargin=2,slotYOffset=30)
    sw4=KeySwitchHole("Keyswitch4",xMargin=1,yMargin=2,slotYOffset=15)
    sw5=KeySwitchHole("Keyswitch5",xMargin=1,yMargin=2,slotYOffset=0)
    sw6=KeySwitchHole("Keyswitch6",xMargin=5,yMargin=5,slotYOffset=0)
```
If you want to move the keys up and down within their columns you just need to change the values of the offsets. For **keyswitch1** change the value of **yMargin**, for the other keys change the value of **slotYOffset**. This complication is due to the way that the autolayout positions items based on their sizes and margins. 
## Setting the size of the key areas
Line 3135 in the current version of BoxMacro.
```
#  Adjust these values to change the overall size of the key
    boardHeight = 21.0
    boardWidth = 21.0
# Adjust these to change the size of the key hole
    slotHeight=14.5
    slotWidth=14.5
```
If you want to change the size of the key positions (which will make the overall size of the box smaller) you can change the **boardheight** and **boardWidth** values. Be careful not to make them too small, as then the keys might crash into each other. 