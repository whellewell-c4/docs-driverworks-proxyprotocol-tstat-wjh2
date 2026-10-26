## DEC\_SETPOINT\_COOL

Decreases the cool setpoint. This command is handled by the proxy. If `can_inc_dec_setpoints` is true, the proxy sends a `DEC_SETPOINT_COOL` command to the protocol driver; otherwise, it handles the decrement locally. If the scale is Fahrenheit, the setpoint is decreased by the value received in the `COOL_SETPOINT_RESOLUTION_F` notification (default: 1). If the scale is Celsius, it is decreased by the value received in the `COOL_SETPOINT_RESOLUTION_C` notification (default: 1).


### Name

`DEC_SETPOINT_COOL ()`


### Parameter

`None`


### Command Sent to Protocol Driver

`SET_SETPOINT_COOL` - sends the new cool setpoint value to the protocol driver.


### Returns

`None`


