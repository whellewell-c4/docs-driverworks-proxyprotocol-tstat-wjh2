## SET_SETPOINT_COOL

Sets the cool setpoint.

### Name

`SET_SETPOINT_COOL ()`

### Parameters

| Parameter    | Type  | Description                                                                        |
| ------------ | ----- | ---------------------------------------------------------------------------------- |
| `FAHRENHEIT` | LEVEL | Optional. Cool setpoint in Fahrenheit.                                             |
| `CELSIUS`    | LEVEL | Optional. Cool setpoint in Celsius.                                                |

### Notes

- At least one temperature parameter must be supplied.
- The proxy clamps the requested value to the thermostat’s supported cool setpoint range and resolution.
- If the thermostat supports both Fahrenheit and Celsius, the proxy accepts whichever scale is provided and converts as needed.
- For this command, the proxy updates the current cool setpoint and sends the corresponding protocol-driver command.


### Command Sent to Protocol Driver

`SET_SETPOINT_COOL` - sends the cool setpoint value to the protocol driver.

### Returns

`None`
