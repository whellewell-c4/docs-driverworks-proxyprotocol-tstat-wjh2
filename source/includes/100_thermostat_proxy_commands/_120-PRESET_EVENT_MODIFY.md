## PRESET\_EVENT\_MODIFY

Modifies an existing Preset Schedule Event. This command is only valid when the protocol driver supports either the can_preset_schedule capability or the can_fixed_schedule_and_presets capability (4.3.0+).


### Name

`PRESET_EVENT_MODIFY ()`


| Parameter                | Type | Description                                                                                             |
| ------------------------ | ---- | ------------------------------------------------------------------------------------------------------- |
| PRESET                   | STR  | Event Name                                                                                              |
| PRESET_ID (new to 4.3.0) | INT  | Preset ID. Added in 4.3.0. Preferred over PRESET when both are present. Mutually exclusive with PRESET. |
| WEEKDAY:                 | INT  | Day of the week. Valid range is 0-6, with Sunday = 0.                                                   |
| HOUR                     | INT  | 0-23                                                                                                    |
| MINUTE                   | INT  | 0-60                                                                                                    |
| NEW WEEKDAY              | INT  | New day of the week. Valid range is 0-6, with Sunday = 0                                                |
| NEW HOUR                 | INT  | New hour of the day. Valid range is 0-23.                                                               |
| NEW MINUTE               | INT  | New minute of the hour. Valid range is 0-59.                                                            |


### Returns

`None`


### Command Sent to Protocol Driver

`SET_PRESETS` — sends the current preset XML payload to the protocol driver.


### Usage Note

Modifying an event to the same time as a different preset event will result in the different preset event being deleted and the new one being put in at that time.


