## INC\_SETPOINT\_SINGLE

Increases the single setpoint. This command is handled by the proxy. If `can_inc_dec_setpoints` is true, the proxy sends an `INC_SETPOINT_SINGLE` command to the protocol driver; otherwise, it handles the increment locally. If the scale is Fahrenheit, the setpoint is increased by the value received in the `SINGLE_SETPOINT_RESOLUTION_F` notification (default: 1). If the scale is Celsius, it is increased by the value received in the `SINGLE_SETPOINT_RESOLUTION_C` notification (default: 1).

### Name

INC\_SETPOINT\_SINGLE ()`


### Parameter

`None`


### Command Sent to Protocol Driver

`SET_SETPOINT_SINGLE` - sends the new heat setpoint value to the protocol driver.


### Returns

`None`


