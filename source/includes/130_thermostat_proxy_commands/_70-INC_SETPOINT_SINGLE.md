## INC\_SETPOINT\_SINGLE

Increases the single setpoint. This command is handled by the proxy.

If `can_inc_dec_setpoints` is true, the proxy sends an `INC_SETPOINT_SINGLE` command to the protocol driver.

If `can_inc_dec_setpoints` is false, the proxy calculates the new setpoint locally based on the configured resolution and then sends a `SET_SETPOINT_SINGLE` command to the protocol driver with the updated setpoint value.

When the thermostat is in Fahrenheit mode, the increment is based on `SINGLE_SETPOINT_RESOLUTION_F` (typically 1). When it is in Celsius mode, the increment is based on `SINGLE_SETPOINT_RESOLUTION_C` (typically 1).


### Name

`INC_SETPOINT_SINGLE ()`


### Parameter

`None`


### Command Sent to Protocol Driver

If `can_inc_dec_setpoints` is true: `INC_SETPOINT_SINGLE`
If `can_inc_dec_setpoints` is false: `SET_SETPOINT_SINGLE` with the calculated new setpoint value


### Notification

When the thermostat actually changes the setpoint, the protocol driver should send back a notification in the form:

- `SETPOINT_CHANGED`
- Parameters:
    - `SETPOINT`
    - `SCALE`

See the thermostat setpoint notification documentation for the exact parameter details and valid values.


### Returns

`None`


