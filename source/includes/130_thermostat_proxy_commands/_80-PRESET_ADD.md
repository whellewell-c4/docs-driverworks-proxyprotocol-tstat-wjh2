## PRESET\_ADD

Adds a new Preset Schedule Preset (If protocol driver has the `can_preset_schedule` or `can_fixed_schedule_and_presets` capability)


### Name

`PRESET_ADD ()`


| Parameter                  | Type | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| -------------------------- | ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| NAME                       | STR  | Preset Name. Required.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| PRESET_FIELDS              | XML  | If a UI or Driver sends a bound call with a string that has invalid XML syntax, this field will be set to `<preset_field/>` and an error message will be logged to director.log when this occurs. Note that only a driver OR UI should specify the` _f or c. ` For example: `heat_setpoint_f`, `cool_setpoint_f`, `heat_setpoint_c`, `cool_setpoint_c` but not both. The proxy will auto insert the missing` _f or _c `based on the scales resolution if it detects one side is not supplied. This makes it so UI's and drivers do not need to calculate the correct value for the scale.  However, if a driver or UI does want to calculate it, the proxy will leave the value alone. In the same manner the proxy will not correct or anything if the` _f and _c `do not resolve to the equivalent temperature. |
| PRESET_EDIT (new to 4.3.0) |      | `PRESET_EDIT` is an optional parameter that describes how the preset may be edited by the UI or client. It is passed through the proxy and normalized before being stored.<br><br>Allowed values:<br>- `all` — the preset can be edited in all fields<br>- `name` — only the preset name may be edited<br>- `read_only` — the preset is read-only and cannot be edited<br><br>If this parameter is omitted, the proxy defaults to `all`. The value is not used to change the preset data itself; it is metadata used to control edit permissions and is preserved with the preset definition.                                                                                                                                                                                                                     |


### Command Sent to Protocol Driver

`SET_PRESETS` - sends the current preset XML payload to the protocol driver.


### Returns

`None`
