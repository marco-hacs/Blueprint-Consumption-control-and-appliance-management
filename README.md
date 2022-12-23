# Consumption-control-and-appliance-management

`- Version: 1.0 -` </h1>
# Never without power again
This project was done for **shutting down household appliances by checking the instantaneous absorption in the house**, to avoid the general meter shutdown.

When the instantaneous consumption is greater than the set value, for a customizable time, automation comes into play that performs checks to the selected entities:
- If the entity is *available and **not** in on*.  
- If the entity's device is associated with a sensor with **device class power** it will check if the power draw is greater than **15 w**. If less, the device is considered off, otherwise on and will be added to the list of devices to be turned off.  In the absence of the device_class it will just see the status of the group entity (on/off).

	This in my opinion is a nice part of the project because we imagine that we are controlling a washing machine, generally we leave the switch on, even if the washing machine is off and thanks to the absorption control we can see if it is really running. 

Once filtered the appliances will start to turn off one at a time respecting the order of the selection and the set waiting time.
 
 When the process is finished and consumption is within limits for a customizable time, the turned off appliances will be turned back on (from the last one turned off to the first one).  


You can receive a notification for each automation step (Push, TTS, Alex).  
  
## Installation
As a first step, you need to enter the <i>[pkg_consumption_control_and_appliance_management.yaml](https://github.com/marco-hacs/Consumption-control-and-appliance-management/blob/main/pkg_consumption_control_and_appliance_management.yaml)</i> in the folder <i>[package](https://www.home-assistant.io/docs/configuration/packages/)</i>, restart HomeAssistant and import the <i>[project](https://github.com/marco-hacs/Consumption-control-and-appliance-management/blob/main/consumption_control_and_appliance_management.yaml)</i>.  
In case you cannot import the file into the packages it is possible to replicate the entities **maintaining the entity_id** contained in the <i>[file](https://github.com/marco-hacs/Consumption-control-and-appliance-management/blob/main/pkg_consumption_control_and_appliance_management.yaml)</i>
  
This is my first project that I'm sharing, and I haven't yet found a way to avoid using external helpers.


