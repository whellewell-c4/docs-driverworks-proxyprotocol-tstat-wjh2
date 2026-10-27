## DEC\_SETPOINT\_HEAT

Decreases the heat setpoint. This command is handled by the proxy.

If `can_inc_dec_setpoints` is true, the proxy sends an `DEC_SETPOINT_HEAT` command to the protocol driver. 

If `can_inc_dec_setpoints` is false, the proxy calculates the new heat setpoint locally based on the configured resolution and then sends a `SET_SETPOINT_HEAT` command to the protocol driver with the updated value.

When the thermostat is in Fahrenheit mode, the setpoint is increased by the value in `HEAT_SETPOINT_RESOLUTION_F` (typically 1). When it is in Celsius mode, it is increased by the value in `HEAT_SETPOINT_RESOLUTION_C` (typically 1).


### Name

`DEC_SETPOINT_HEAT ()`


### Parameter

`None`


### Command Sent to Protocol Driver

If `can_inc_dec_setpoints` is true: `DEC_SETPOINT_HEAT`
If `can_inc_dec_setpoints` is false: `SET_SETPOINT_HEAT` with the calculated new setpoint value


### Notification

When the thermostat actually changes the heat setpoint, the protocol driver should send back a notification in the form:

- `HEAT_SETPOINT_CHANGED`
- Parameters:
    - `SETPOINT`
    - `SCALE`


### Returns

`None`


