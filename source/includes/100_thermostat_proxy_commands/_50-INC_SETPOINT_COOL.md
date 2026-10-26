## INC\_SETPOINT\_COOL

Increases the cool setpoint. This command is handled by the proxy. If `can_inc_dec_setpoints` is true, the proxy sends a `INC_SETPOINT_COOL` command to the protocol driver; otherwise, it handles the increment locally. If the scale is Fahrenheit, the setpoint is increased by the value received in the `COOL_SETPOINT_RESOLUTION_F` notification (default: 1). If the scale is Celsius, it is decreased by the value received in the `COOL_SETPOINT_RESOLUTION_C` notification (default: 1).

Used to increase the cool set point by 1. This command is handled by the proxy, and ends up creating a `SET_SETPOINT_COOL` command to send to the protocol driver, unless the capability `can_inc_dec_setpoints` is set to true.


### Name

`INC_SETPOINT_COOL ()`


### Parameter

`None`


### Command Sent to Protocol Driver

`SET_SETPOINT_COOL` - sends the new cool setpoint value to the protocol driver.


### Returns

`None`


