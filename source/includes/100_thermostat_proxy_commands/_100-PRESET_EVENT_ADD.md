## PRESET\_EVENT\_ADD

Adds a preset schedule event to run at the specified day and time. This command is only valid when the protocol driver supports either the can_preset_schedule capability or the can_fixed_schedule_and_presets capability (4.3.0+).

### Name

`PRESET_EVENT_ADD ()`


| Parameter                | Description | Description                                                                                             |
| ------------------------ | ----------- | ------------------------------------------------------------------------------------------------------- |
| PRESET                   | STR         | Preset name. Required before 4.3.0. In 4.3.0+, this is mutually exclusive with PRESET_ID.               |
| PRESET_ID (new to 4.3.0) | INT         | Preset ID. Added in 4.3.0. Preferred over PRESET when both are present. Mutually exclusive with PRESET. |
| WEEKDAY                  | INT         | Day of the week. Valid range is 0-6, with Sunday = 0.                                                   |
| HOUR                     | INT         | Hour of the day. Valid range is 0-23.                                                                   |
| MINUTE                   | INT         | Minute of the hour. Valid range is 0-59.                                                                |


### Returns

`None`


### Command Sent to Protocol Driver

`SET_PRESETS` — sends the current preset XML payload to the protocol driver.



### Usage Note

Adding an event at the same time as a different preset event will result in the different preset event being deleted and the new one being put in at that time.
