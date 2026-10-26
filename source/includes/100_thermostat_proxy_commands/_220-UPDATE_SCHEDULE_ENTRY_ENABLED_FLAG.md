
## SET_SETPOINT_SINGLE

Sets the single setpoint.

### Name
SET_SETPOINT_SINGLE ()

  

| Parameter    | Type  | Description                                                                          |
| ------------ | ----- | ------------------------------------------------------------------------------------ |
| `FAHRENHEIT` | LEVEL | Optional. Single setpoint in Fahrenheit.                                             |
| `CELSIUS`    | LEVEL | Optional. Single setpoint in Celsius.                                                |

### Notes

- At least one temperature parameter must be supplied.
- The proxy clamps the requested value to the thermostat’s supported single-setpoint range and resolution.
- If the thermostat supports both Fahrenheit and Celsius, the proxy accepts whichever scale is provided and converts as needed.
- This command is used for thermostats that expose a single active setpoint rather than separate heat/cool setpoints.

### Command Sent to Protocol Driver

`SET_SETPOINT_SINGLE` - sends the single setpoint value to the protocol driver.

### Returns

`None`

