## SET_SETPOINT_HEAT

Sets the heat setpoint.

### Name

`SET_SETPOINT_HEAT ()`

### Parameters

| Parameter    | Type  | Description                                                                        |
| ------------ | ----- | ---------------------------------------------------------------------------------- |
| `FAHRENHEIT` | LEVEL | Optional. Heat setpoint in Fahrenheit.                                             |
| `CELSIUS`    | LEVEL | Optional. Heat setpoint in Celsius.                                                |

### Notes

- At least one temperature parameter must be supplied.
- The proxy clamps the requested value to the thermostat’s supported heat setpoint range and resolution.
- If the thermostat supports both Fahrenheit and Celsius, the proxy accepts whichever scale is provided and converts as needed.


### Command Sent to Protocol Driver

`SET_SETPOINT_HEAT` - sends the heat setpoint value to the protocol driver.

### Returns

`None`
