# How To Setup A MSFS2020 Button Box
Guide on setting up a button box for Microsoft Flight Simulator. For DaGodz and friends.

# What's a button box?
A button box is simply a collection of external buttons, switches, dials etc that have been wired together into a board that can act as a HID device (boards like the Arduino Leaonardo or Pro Micro that use the atmega32u4 does this). The board then has its firmware updated so that activated the various inputs will cause code to be run. On the other side of things, Microsoft Flight Simulator has an SDK that allows external applications to get data from it and send inputs. More on that below. This document doesn't cover creating the physical circuits, there are plenty of YouTube videos on that.

# Software you will need
* Microsoft Flight Simulator 2020 (or any previous version, XPlane etc) - The game/sim.
* FSUIPC7 - Acts as a gateway for input events from your button box and output events from the Sim.
* MobiFlight - Provides easy to use configuration for FSUIPC to upload to your button box controller board.
* Arduino IDE - Configures the communication with your Arduino or equivalent board.

# How to set it up
1. Plug in your button box.
2. Open the Arduino IDE and select the right board variant and COM port.
3. Open MobiFlight > Extras > Settings >  MobiFlight Modules and configure the components of your button box. 
   * Don't forget to upload your configuration to the board by clicking the Upload button.
4. Configure MobiFlight on the main window by adding Inputs/Outputs as needed.
   * In testing, I have found that using the preset Event ID items is nice and easy.
5. Open FSUIPC7.
6. Start the Sim. 
7. Enjoy!
