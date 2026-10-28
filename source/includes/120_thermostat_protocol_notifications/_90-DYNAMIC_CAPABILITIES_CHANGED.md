## DYNAMIC\_CAPABILITIES\_CHANGED


Dynamic Capabilities is a way for a protocol driver to send updates about some thermostat capabilities that can be changed when settings change on the hardware.  An example would be a thermostat that has a humidifier added and would need to tell the proxy it can now do humidification as well as what the min, max, resolution and other changes are for the setpoint. 

There are two types of capabilities, static and dynamic. 

Static capabilities are defined in the `<capabilities>` section of the driver's driver.xml file and are immutable. For a complete list of Thermostat capabilities, please see the [Thermostat Proxy Capabilities][1] section.

Dynamic capabilities, as discussed in this section, are updated by the driver through the C4:SendToProxy() command. See the Lua Example below.  A Lua table needs to be created defining the parameter name and it's value.  Dynamic capabilities are not required to be in the driver.xml file. If it is not included it will initialize with the default value and can be updated at any time by the driver. If the thermostat device does not support changing the configuration then it is recommended it be used as a static capability. Listed in the table below are all of the possible `DYNAMIC_CAPABILITIES_CHANGED` notification parameters. The Capability column lists the capability associated with the notification that will be updated. For a more detailed list of the Dynamic Capability Notifications, please see  [Thermostat Dynamic Notifications][2] section.


### Name

`DYNAMIC_CAPABILITIES_CHANGED ()`


### Dynamic Capability Notifications

| Parameter                          | Type             | Default     | Capability                         |
| ---------------------------------- | ---------------- | ----------- | ---------------------------------- |
| `CAN_AUTO`                         | boolean          | false       | `can_do_auto`                      |
| `CAN_CHANGE_SCALE`                 | boolean          | true        | `can_change_scale`                 |
| `CAN_COOL`                         | boolean          | false       | `can_cool`                         |
| `CAN_DEHUMIDIFY`                   | boolean          | false       | `can_dehumidify`                   |
| `CAN_FIXED_SCHEDULE_AND_PRESETS`   | boolean          | false       | `can_fixed_schedule_and_presets`   |
| `CAN_HEAT`                         | boolean          | true        | `can_heat`                         |
| `CAN_HUMIDIFY`                     | boolean          | false       | `can_humidify`                     |
| `CAN_LOCK_SCREEN`                  | boolean          | false       | `can_lock_screen`                  |
| `CAN_PRESET`                       | boolean          | false       | `can_preset`                       |
| `CAN_PRESET_SCHEDULE`              | boolean          | false       | `can_preset_schedule`              |
| `COOL_SETPOINT_MAX_C`              | double as string | 100         | `setpoint_cool_max_c`              |
| `COOL_SETPOINT_MAX_F`              | double as string | 100         | `setpoint_cool_max_f`              |
| `COOL_SETPOINT_MIN_C`              | double as string | 0           | `setpoint_cool_min_c`              |
| `COOL_SETPOINT_MIN_F`              | double as string | 0           | `setpoint_cool_min_f`              |
| `COOL_SETPOINT_RESOLUTION_C`       | double as string | 1           | `setpoint_cool_resolution_c`       |
| `COOL_SETPOINT_RESOLUTION_F`       | double as string | 1           | `setpoint_cool_resolution_f`       |
| `DEHUMIDIFY_SETPOINT_MAX`          | integer          | 100         | `setpoint_dehumidify_max`          |
| `DEHUMIDIFY_SETPOINT_MIN`          | integer          | 0           | `setpoint_dehumidify_min`          |
| `DEHUMIDIFY_SETPOINT_RESOLUTION`   | integer          | 1           | `setpoint_dehumidify_resolution`   |
| `HAS_EXTRAS`                       | boolean          | false       | `has_extras`                       |
| `HAS_HEAT_PUMP`                    | boolean          | false       | `has_heat_pump`                    |
| `HAS_HUMIDITY`                     | boolean          | false       | `has_humidity`                     |
| `HAS_OUTDOOR_TEMPERATURE`          | boolean          | false       | `has_outdoor_temperature`          |
| `HAS_SCHEDULE`                     | boolean          | false       | `has_schedule`                     |
| `HAS_SINGLE_SETPOINT`              | boolean          | false       | `has_single_setpoint`              |
| `HAS_TEMPERATURE`                  | boolean          | true        | `has_temperature`                  |
| `HEAT_SETPOINT_MAX_C`              | double as string | 100         | `setpoint_heat_max_c`              |
| `HEAT_SETPOINT_MAX_F`              | double as string | 100         | `setpoint_heat_max_f`              |
| `HEAT_SETPOINT_MIN_C`              | double as string | 0           | `setpoint_heat_min_c`              |
| `HEAT_SETPOINT_MIN_F`              | double as string | 0           | `setpoint_heat_min_f`              |
| `HEAT_SETPOINT_RESOLUTION_C`       | double as string | 1           | `setpoint_heat_resolution_c`       |
| `HEAT_SETPOINT_RESOLUTION_F`       | double as string | 1           | `setpoint_heat_resolution_f`       |
| `HEATCOOL_SETPOINTS_DEADBAND_C`    | double as string | 2           | `setpoint_heatcool_deadband_c`     |
| `HEATCOOL_SETPOINTS_DEADBAND_F`    | double as string | 2           | `setpoint_heatcool_deadband_f`     |
| `HOLD_UNTIL_MODE`                  | string           | `date,time` | `hold_until_mode`                  |
| `HOLD_UNTIL_RESOLUTION`            | integer          | 5           | `hold_until_resolution`            |
| `HUMIDIFY_SETPOINT_MAX`            | integer          | 100         | `setpoint_humidify_max`            |
| `HUMIDIFY_SETPOINT_MIN`            | integer          | 0           | `setpoint_humidify_min`            |
| `HUMIDIFY_SETPOINT_RESOLUTION`     | integer          | 1           | `setpoint_humidify_resolution`     |
| `HUMIDITY_RESOLUTION`              | integer          | 1           | `humidity_resolution`              |
| `HUMIDITY_SETPOINTS_DEADBAND`      | integer          | 10          | `setpoint_humidity_deadband`       |
| `LOCK_SCREEN_MODES`                | string           | ""          | `lock_screen_modes`                |
| `OUTDOOR_TEMPERATURE_RESOLUTION_C` | double as string | 1           | `outdoor_temperature_resolution_c` |
| `OUTDOOR_TEMPERATURE_RESOLUTION_F` | double as string | 1           | `outdoor_temperature_resolution_f` |
| `SINGLE_SETPOINT_MAX_C`            | double as string | 100         | `setpoint_single_max_c`            |
| `SINGLE_SETPOINT_MAX_F`            | double as string | 100         | `setpoint_single_max_f`            |
| `SINGLE_SETPOINT_MIN_C`            | double as string | 0           | `setpoint_single_min_c`            |
| `SINGLE_SETPOINT_MIN_F`            | double as string | 0           | `setpoint_single_min_f`            |
| `SINGLE_SETPOINT_RESOLUTION_C`     | double as string | 1           | `setpoint_single_resolution_c`     |
| `SINGLE_SETPOINT_RESOLUTION_F`     | double as string | 1           | `setpoint_single_resolution_f`     |
| `TEMPERATURE_MAX_C`                | double as string | 50          | `current_temperature_max_c`        |
| `TEMPERATURE_MAX_F`                | double as string | 120         | `current_temperature_max_f`        |
| `TEMPERATURE_MIN_C`                | double as string | -40         | `current_temperature_min_c`        |
| `TEMPERATURE_MIN_F`                | double as string | -40         | `current_temperature_min_f`        |
| `TEMPERATURE_RESOLUTION_C`         | double as string | 1           | `current_temperature_resolution_c` |
| `TEMPERATURE_RESOLUTION_F`         | double as string | 1           | `current_temperature_resolution_f` |


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




[1]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
[2]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-protocol-dynamic-notifications