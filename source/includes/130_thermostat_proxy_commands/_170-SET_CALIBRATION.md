## SET_CALIBRATION


### Name

`SET_CALIBRATION ()`


| Parameter     | Type | Description                               |
| ------------- | ---- | ----------------------------------------- |
| `CALIBRATION` | INT  | Required. The calibration value to apply. |

### Notes

- This command is only valid when the thermostat supports calibration.
- The proxy updates the in-memory calibration value and forwards the value to the protocol driver using the thermostat’s native command format.
- Calibration is a driver/hardware-level adjustment and is not a UI-only setting.


### Command Sent to Protocol Driver

`SET_CALIBRATION` - sends the calibration value to the protocol driver.

### Returns

`None`

