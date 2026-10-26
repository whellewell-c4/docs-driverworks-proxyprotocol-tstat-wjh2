## PRESET\_MODIFY

Modifies an existing Preset Schedule Event. This command is only valid when the protocol driver supports either the can_preset_schedule capability or the can_fixed_schedule_and_presets capability (4.3.0+).


### Name

`PRESET_MODIFY ()`


| Parameter                | Type | Description                                                                                             |
| ------------------------ | ---- | ------------------------------------------------------------------------------------------------------- |
| NAME                     | STR  | Preset Name. In 4.3.0+, this is mutually exclusive with PRESET_ID.                                      |
| PRESET_ID (new to 4.3.0) | INT  | Preset ID. Added in 4.3.0. Preferred over PRESET when both are present. Mutually exclusive with PRESET. |
| PRESET_FIELDS            | XML  | XML DATA                                                                                                |
| NEW_NAME                 | STR  | New Preset Name                                                                                         |

### Returns

`None`


### Command Sent to Protocol Driver

`SET_PRESETS` — sends the current preset XML payload to the protocol driver.


### Example

```lua
<preset_fields>
  <field id="heat_setpoint_f" value="65">
  <field id="cool_setpoint_f" value="75">
  <field id="humidify_setpoint" value="50">
  <field id="fan_mode" value="On">
</preset_fields>
```




