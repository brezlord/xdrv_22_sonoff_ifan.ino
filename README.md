# xdrv_22_sonoff_ifan.ino
Custom edit of the Tasmota xdrv_22_sonoff_ifan.ino file to allow custom control of a AC ceiling fan.

This template will allow to use GPIO 3 as a push button to control the fan from the wall plate. This will disable the RF:433.92MHz chip so the remote will not work.

{"NAME":"Sonoff iFan03","GPIO":[32,3200,0,34,0,0,256,512,226,320,225,227,0,0],"FLAG":0,"BASE":71}

Once the controller has rebooted we need to create a rule that will cycle through the fan speeds 1 step at a time from off to Low to MED to HI and back to off with each button press.

To do this go the controllers web config page and click on the console button the enter the bellow rule and press enter.

rule1 on button3#state do FanSpeed + endon

Now to enable the rule run the bellow command in the console and press enter.

Rule1 1

If you want the light and fan to be off when you power up the controller, run the below command in the console and press enter.

PowerOnState 0
