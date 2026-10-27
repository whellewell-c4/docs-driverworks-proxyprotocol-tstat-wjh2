### Name

`SET_LOCK_SCREEN_MODE ()`

### Parameters

|Parameter|Type|Description|
|---|---|---|
|`MODE`|STR|Required. The lock screen mode to apply.|

### Notes

- This command is new in 4.3.0.
- The valid values for `MODE` are defined by the thermostat capability `lock_screen_modes`.
	- Example:
```xml
	  <lock_screen_modes>Unlocked,Partially Locked,Fully Locked</lock_screen_modes>
```
- The value passed to the command must match one of the supported lock screen modes reported by the thermostat.


### Command Sent to Protocol Driver

`SET_LOCK_SCREEN_MODE` - sends the mode value to the protocol driver.

### Returns

`None`