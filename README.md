# How To Setup A MSFS2020 Button Box
Guide on setting up a button box for Microsoft Flight Simulator. For DaGodz and friends.

# What's a button box?
A button box is simply a collection of external buttons, switches, dials etc that have been wired together into a board that can act as a HID device (boards like the Arduino Leaonardo or Pro Micro that use the atmega32u4 does this). The board then has its firmware updated so that activated the various inputs will cause code to be run. On the other side of things, Microsoft Flight Simulator has an SDK that allows external applications to get data from it and send inputs. More on that below. This document doesn't cover creating the physical circuits, there are plenty of YouTube videos on that.

# Software you will need
* Microsoft Flight Simulator 2020 (or any previous version, XPlane etc) - The game/sim.
* [FSUIPC7 BETA](https://forum.simflight.com/topic/90193-fsuipc7-beta-for-msfs/ "FSUIPC7 BETA Download Thread") - Acts as a gateway for input events from your button box and output events from the Sim.
* [MobiFlight](https://www.mobiflight.com/en/download.html "MobiFlight Download Page") - Provides easy to use configuration for FSUIPC to upload to your button box controller board.
* [Arduino IDE](https://www.arduino.cc/en/Main/Software "Arduino IDE Download Page") - Configures the communication with your Arduino or equivalent board.

# How it works
MobiFlight uses the Arudiono IDE configuration (not shown below) to update the firmware of the controller board. The board then sends signals based on inputs from the buttons, switches, encoders etc to MobiFlight. MobiFlight in turn translates these to events that FSUIPC7 can see, which in turn sends those events into the SDK/SimConnect (it's not completely clear if these are the same thing), which passes them onto the Sim. The same is true in reverse, which allows for events in the game to causes changes on your physical button box, like making LEDs change and displays to show information. Neat huh!?
![Alt](/button-box-to-msfs2020-flow-diagram.svg "Diagram showing how the different software work together")

# How to set it up
1. Plug in your button box.
2. Open the Arduino IDE and select the right board variant and COM port.
3. Open `MobiFlight > Extras > Settings >  MobiFlight Modules` and configure the components of your button box. 
   * Don't forget to upload your configuration to the board by clicking the `Upload` button.
4. Configure MobiFlight on the main window by adding Inputs/Outputs as needed.
   * In testing, I have found that using the preset `Event ID` items is nice and easy.
5. Open FSUIPC7.
6. Click `Run` on MobiFlight.
7. Start the Sim. 
8. Enjoy!

# Examples
1. [Nick's Knob Box](/examples/nicks-knob-box "Example Nick's Knob Box")
