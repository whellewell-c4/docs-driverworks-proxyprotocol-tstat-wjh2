## DYNAMIC\_CAPABILITIES\_CHANGED


Dynamic Capabilities is a way for a protocol driver to send updates about some thermostat capabilities that can be changed when settings change on the hardware.  An example would be a thermostat that has a humidifier added and would need to tell the proxy it can now do humidification as well as what the min, max, resolution and other changes are for the setpoint. 

There are two types of capabilities, static and dynamic. 

Static capabilities are defined in the `<capabilities>` section of the driver's driver.xml file and are immutable. For a complete list of Thermostat capabilities, please see the [Thermostat Proxy Capabilities][1] section.

Dynamic capabilities, as discussed in this section, are updated by the driver through the C4:SendToProxy() command. See the Lua Example below.  A Lua table needs to be created defining the parameter name and it's value.  Dynamic capabilities are not required to be in the driver.xml file. If it is not included it will initialize with the default value and can be updated at any time by the driver. If the thermostat device does not support changing the configuration then it is recommended it be used as a static capability. Listed in the table below are all of the possible `DYNAMIC_CAPABILITIES_CHANGED` notification parameters. The Capability column lists the capability associated with the notification that will be updated. For a more detailed list of the Dynamic Capability Notifications, please see  [Thermostat Dynamic Notifications][2] section.


### Name

`DYNAMIC_CAPABILITIES_CHANGED ()`


### Dynamic Capability Notifications

| Parameter                              | Type   | Default     | Capability                         |
| -------------------------------------- | ------ | ----------- | ---------------------------------- |
| [CAN_AUTO][3]                          | BOOL   | false       | `can_do_auto`                      |
| [CAN_CHANGE_SCALE][4]                  | BOOL   | true        | `can_change_scale`                 |
| [CAN_COOL][5]                          | BOOL   | false       | `can_cool`                         |
| [CAN_DEHUMIDIFY][6]                    | BOOL   | false       | `can_dehumidify`                   |
| [CAN_FIXED_SCHEDULE_AND_PRESETS][7]    | BOOL   | false       | `can_fixed_schedule_and_presets`   |
| [CAN_HEAT][8]                          | BOOL   | true        | `can_heat`                         |
| [CAN_HUMIDIFY][9]                      | BOOL   | false       | `can_humidify`                     |
| [CAN_LOCK_SCREEN][10]                  | BOOL   | false       | `can_lock_screen`                  |
| [CAN_PRESET][11]                       | BOOL   | false       | `can_preset`                       |
| [CAN_PRESET_SCHEDULE][12]              | BOOL   | false       | `can_preset_schedule`              |
| [COOL_SETPOINT_MAX_C][13]              | INT    | 100         | `setpoint_cool_max_c`              |
| [COOL_SETPOINT_MAX_F][14]              | INT    | 100         | `setpoint_cool_max_f`              |
| [COOL_SETPOINT_MIN_C][15]              | INT    | 0           | `setpoint_cool_min_c`              |
| [COOL_SETPOINT_MIN_F][16]              | INT    | 0           | `setpoint_cool_min_f`              |
| [COOL_SETPOINT_RESOLUTION_C][17]       | INT    | 1           | `setpoint_cool_resolution_c`       |
| [COOL_SETPOINT_RESOLUTION_F][18]       | INT    | 1           | `setpoint_cool_resolution_f`       |
| [DEHUMIDIFY_SETPOINT_MAX][19]          | INT    | 100         | `setpoint_dehumidify_max`          |
| [DEHUMIDIFY_SETPOINT_MIN][20]          | INT    | 0           | `setpoint_dehumidify_min`          |
| [DEHUMIDIFY_SETPOINT_RESOLUTION][21]   | INT    | 1           | `setpoint_dehumidify_resolution`   |
| [HAS_EXTRAS][22]                       | BOOL   | false       | `has_extras`                       |
| [HAS_HEAT_PUMP][23]                    | BOOL   | false       | `has_heat_pump`                    |
| [HAS_HUMIDITY][24]                     | BOOL   | false       | `has_humidity`                     |
| [HAS_OUTDOOR_TEMPERATURE][25]          | BOOL   | false       | `has_outdoor_temperature`          |
| [HAS_SCHEDULE][26]                     | BOOL   | false       | `has_schedule`                     |
| [HAS_SINGLE_SETPOINT][27]              | BOOL   | false       | `has_single_setpoint`              |
| [HAS_TEMPERATURE][28]                  | BOOL   | true        | `has_temperature`                  |
| [HEATCOOL_SETPOINTS_DEADBAND_C][29]    | INT    | 2           | `setpoint_heatcool_deadband_c`     |
| [HEATCOOL_SETPOINTS_DEADBAND_F][30]    | INT    | 2           | `setpoint_heatcool_deadband_f`     |
| [HEAT_SETPOINT_MAX_C][31]              | INT    | 100         | `setpoint_heat_max_c`              |
| [HEAT_SETPOINT_MAX_F][32]              | INT    | 100         | `setpoint_heat_max_f`              |
| [HEAT_SETPOINT_MIN_C][33]              | INT    | 0           | `setpoint_heat_min_c`              |
| [HEAT_SETPOINT_MIN_F][34]              | INT    | 0           | `setpoint_heat_min_f`              |
| [HEAT_SETPOINT_RESOLUTION_C][35]       | INT    | 1           | `setpoint_heat_resolution_c`       |
| [HEAT_SETPOINT_RESOLUTION_F][36]       | INT    | 1           | `setpoint_heat_resolution_f`       |
| [HOLD_UNTIL_MODE][37]                  | STRING | `date,time` | `hold_until_mode`                  |
| [HOLD_UNTIL_RESOLUTION][38]            | INT    | 5           | `hold_until_resolution`            |
| [HUMIDITY_SETPOINTS_DEADBAND][39]      | INT    | 10          | `setpoint_humidity_deadband`       |
| [HUMIDIFY_SETPOINT_MAX][40]            | INT    | 100         | `setpoint_humidify_max`            |
| [HUMIDIFY_SETPOINT_MIN][41]            | INT    | 0           | `setpoint_humidify_min`            |
| [HUMIDIFY_SETPOINT_RESOLUTION][42]     | INT    | 1           | `setpoint_humidify_resolution`     |
| [HUMIDITY_RESOLUTION][43]              | INT    | 1           | `humidity_resolution`              |
| [LOCK_SCREEN_MODES][44]                | STRING | ""          | `lock_screen_modes`                |
| [OUTDOOR_TEMPERATURE_RESOLUTION_C][45] | INT    | 1           | `outdoor_temperature_resolution_c` |
| [OUTDOOR_TEMPERATURE_RESOLUTION_F][46] | INT    | 1           | `outdoor_temperature_resolution_f` |
| [SINGLE_SETPOINT_MAX_C][47]            | INT    | 100         | `setpoint_single_max_c`            |
| [SINGLE_SETPOINT_MAX_F][48]            | INT    | 100         | `setpoint_single_max_f`            |
| [SINGLE_SETPOINT_MIN_C][49]            | INT    | 0           | `setpoint_single_min_c`            |
| [SINGLE_SETPOINT_MIN_F][50]            | INT    | 0           | `setpoint_single_min_f`            |
| [SINGLE_SETPOINT_RESOLUTION_C][51]     | INT    | 1           | `setpoint_single_resolution_c`     |
| [SINGLE_SETPOINT_RESOLUTION_F][52]     | INT    | 1           | `setpoint_single_resolution_f`     |
| [TEMPERATURE_MAX_C][53]                | INT    | 50          | `current_temperature_max_c`        |
| [TEMPERATURE_MAX_F][54]                | INT    | 120         | `current_temperature_max_f`        |
| [TEMPERATURE_MIN_C][55]                | INT    | -40         | `current_temperature_min_c`        |
| [TEMPERATURE_MIN_F][56]                | INT    | -40         | `current_temperature_min_f`        |
| [TEMPERATURE_RESOLUTION_C][57]         | INT    | 1           | `current_temperature_resolution_c` |
| [TEMPERATURE_RESOLUTION_F][58]         | INT    | 1           | `current_temperature_resolution_f` |


### Lua example

```lua
local CanHeat = true

local Params = {
    CAN_HEAT = tostring(CanHeat)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```




[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-protocol-dynamic-notifications
[3]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_auto
[4]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_change_scale
[5]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_cool
[6]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_dehumidify
[7]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_fixed_schedule_and_presets
[8]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_heat
[9]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_humidify
[10]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_lock_screen
[11]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_preset
[12]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-can_preset_schedule
[13]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-cool_setpoint_max_c
[14]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-cool_setpoint_max_f
[15]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-cool_setpoint_min_c
[16]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-cool_setpoint_min_f
[17]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-cool_setpoint_resolution_c
[18]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-cool_setpoint_resolution_f
[19]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-dehumidify_setpoint_max
[20]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-dehumidify_setpoint_min
[21]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-dehumidify_setpoint_resolution
[22]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-has_extras
[23]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-has_heat_pump
[24]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-has_humidity
[25]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-has_outdoor_temperature
[26]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-has_schedule
[27]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-has_single_setpoint
[28]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-has_temperature
[29]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heatcool_setpoints_deadband_c
[30]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heatcool_setpoints_deadband_f
[31]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heat_setpoint_max_c
[32]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heat_setpoint_max_f
[33]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heat_setpoint_min_c
[34]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heat_setpoint_min_f
[35]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heat_setpoint_resolution_c
[36]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-heat_setpoint_resolution_f
[37]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-hold_until_mode
[38]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-hold_until_resolution
[39]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-humidity_setpoints_deadband
[40]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-humidify_setpoint_max
[41]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-humidify_setpoint_min
[42]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-humidify_setpoint_resolution
[43]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-humidity_resolution
[44]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-lock_screen_modes
[45]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-outdoor_temperature_resolution_c
[46]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-outdoor_temperature_resolution_f
[47]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-single_setpoint_max_c
[48]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-single_setpoint_max_f
[49]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-single_setpoint_min_c
[50]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-single_setpoint_min_f
[51]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-single_setpoint_resolution_c
[52]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-single_setpoint_resolution_f
[53]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-temperature_max_c
[54]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-temperature_max_f
[55]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-temperature_min_c
[56]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-temperature_min_f
[57]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-temperature_resolution_c
[58]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-dynamic-notifications-temperature_resolution_f

