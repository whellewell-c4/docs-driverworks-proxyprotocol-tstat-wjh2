## PRESET\_DELETE

Deletes an existing preset. Preset delete is enabled in the UIs if `can_preset_schedule` or `can_fixed_schedule_and_presets` capability is enabled. PRESET_ID was introduced in 4.3.0.  Do not use PRESET_ID if the driver supports earlier versions.

The preferred identifier is `PRESET_ID`; it is used instead of `NAME` when both are present. `PRESET_ID` and `NAME` are mutually exclusive, and the command rejects the request if neither is supplied. 

If `PRESET_ID` is provided, the proxy clears `NAME` and deletes the matching preset by ID. If `PRESET_ID` is absent, it deletes the preset matching the provided `NAME`. This follows the 4.3.0 behavior, where `PRESET_ID` was added as the preferred parameter for preset deletion.


### Name

`PRESET_DELETE ()`


| Parameter                | Type | Description                                                             |
| ------------------------ | ---- | ----------------------------------------------------------------------- |
| NAME                     | STR  | Preset Name. Before 4.3.0 is Required. 4.3.0+ it is Mutually exclusive. |
| PRESET_ID (new to 4.3.0) | INT  | Preset ID. Preferred parameter. Mutually exclusive                      |


### Command Sent to Protocol Driver

`SET_PRESETS` - sends the current preset XML payload to the protocol driver.


### Returns

`None`


