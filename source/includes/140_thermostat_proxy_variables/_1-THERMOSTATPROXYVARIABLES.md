## THERMOSTAT PROXY VARIABLES
Thermostats that use this proxy have the following registered variables that can be manipulated.
Note: Temperature units are stored and processed in the proxy as current units, Celsius * 10.

### COOL_SETPOINT
Current cool setpoint.

**Variable ID:** 1103
**Type:** int
**Read Only:** false
**Hidden:** true
**Updated by:** [COOL_SETPOINT_CHANGED][1] and [FORCE_INFO][7] notifications

### COOL_SETPOINT_C
Cool setpoint in Celsius.

**Variable ID:** 1135
**Type:** float
**Read Only:** false
**Hidden:** false
**Updated by:** [COOL_SETPOINT_CHANGED][1] notification

### COOL_SETPOINT_F
Cool setpoint in Fahrenheit.

**Variable ID:** 1134
**Type:** float
**Read Only:** false
**Hidden:** false
**Updated by:** [COOL_SETPOINT_CHANGED][1] notification

### DEHUMIDIFY_SETPOINT
Current dehumidify setpoint.

**Variable ID:** 1143
**Type:** int
**Read Only:** false
**Hidden:** false
**Updated by:** [DEHUMIDIFY_SETPOINT_CHANGED][3] and [FORCE_INFO][7] notifications

### DISPLAY_COOLSETPOINT
Displayed cool setpoint.

**Variable ID:** 1119
**Type:** float
**Read Only:** true
**Hidden:** true
**Updated by:** [COOL_SETPOINT_CHANGED][1] and [FORCE_INFO][7] notifications

### DISPLAY_HEATSETPOINT
Displayed heat setpoint.

**Variable ID:** 1118
**Type:** float
**Read Only:** true
**Hidden:** true
**Updated by:** [HEAT_SETPOINT_CHANGED][4] and [FORCE_INFO][7] notifications

### DISPLAY_TEMPERATURE
Displayed temperature.

**Variable ID:** 1117
**Type:** float
**Read Only:** true
**Hidden:** true
**Updated by:** [TEMPERATURE_CHANGED][5] and [FORCE_INFO][7] notifications

### FAN_MODE
Current fan mode.

**Variable ID:** 1105
**Type:** string
**Read Only:** true
**Hidden:** false
**Updated by:** [FAN_MODE_CHANGED][2], [ALLOWED_FAN_MODES_CHANGED][6], and [FORCE_INFO][7] notifications

### FAN_MODES_LIST
Comma-separated list of supported fan modes.

**Variable ID:** 1121
**Type:** string
**Read Only:** true
**Hidden:** true
**Updated by:** [ALLOWED_FAN_MODES_CHANGED][6] notification

### FAN_STATE
Current fan state.

**Variable ID:** 1108
**Type:** string
**Read Only:** true
**Hidden:** false
**Updated by:** [FAN_STATE_CHANGED][8] and [FORCE_INFO][7] notifications

### HEAT_SETPOINT
Current heat setpoint.

**Variable ID:** 1102
**Type:** int
**Read Only:** false
**Hidden:** true
**Updated by:** [HEAT_SETPOINT_CHANGED][4] and [FORCE_INFO][7] notifications

### HEAT_SETPOINT_C
Heat setpoint in Celsius.

**Variable ID:** 1133
**Type:** float
**Read Only:** false
**Hidden:** false
**Updated by:** [HEAT_SETPOINT_CHANGED][4] notification

### HEAT_SETPOINT_F
Heat setpoint in Fahrenheit.

**Variable ID:** 1132
**Type:** float
**Read Only:** false
**Hidden:** false
**Updated by:** [HEAT_SETPOINT_CHANGED][4] notification

### HEATCOOL_SETPOINTS_DEADBAND_C
Heat/cool deadband in Celsius.

**Variable ID:** 1147
**Type:** float
**Read Only:** true
**Hidden:** false
**Updated by:** [DYNAMIC_CAPABILITIES_CHANGED][9] notification

### HEATCOOL_SETPOINTS_DEADBAND_F
Heat/cool deadband in Fahrenheit.

**Variable ID:** 1146
**Type:** float
**Read Only:** true
**Hidden:** false
**Updated by:** [DYNAMIC_CAPABILITIES_CHANGED][9] notification

### HOLD_MODE
Current hold mode.

**Variable ID:** 1106
**Type:** string
**Read Only:** true
**Hidden:** false
**Updated by:** [HOLD_MODE_CHANGED][10], [ALLOWED_HOLD_MODES_CHANGED][21], and [FORCE_INFO][7] notifications

### HOLD_MODES_LIST
Comma-separated list of hold modes.

**Variable ID:** 1122
**Type:** string
**Read Only:** true
**Hidden:** true
**Updated by:** [ALLOWED_HOLD_MODES_CHANGED][21] notification

### HUMIDIFY_SETPOINT
Current humidify setpoint.

**Variable ID:** 1142
**Type:** int
**Read Only:** false
**Hidden:** false
**Updated by:** [HUMIDIFY_SETPOINT_CHANGED][11] and [FORCE_INFO][7] notifications

### HUMIDITY
Current humidity value.

**Variable ID:** 1138
**Type:** int
**Read Only:** true
**Hidden:** false
**Updated by:** [HUMIDITY_CHANGED][12] and [FORCE_INFO][7] notifications

### HUMIDITY_MODE
Current humidity mode.

**Variable ID:** 1139
**Type:** string
**Read Only:** true
**Hidden:** false
**Updated by:** [HUMIDITY_MODE_CHANGED][13], [ALLOWED_HUMIDITY_MODES_CHANGED][14], and [FORCE_INFO][7] notifications

### HUMIDITY_MODES_LIST
Comma-separated list of supported humidity modes.

**Variable ID:** 1140
**Type:** string
**Read Only:** true
**Hidden:** true
**Updated by:** [ALLOWED_HUMIDITY_MODES_CHANGED][14] notification

### HUMIDITY_SETPOINTS_DEADBAND
Humidity setpoint deadband.

**Variable ID:** 1148
**Type:** int
**Read Only:** true
**Hidden:** false
**Updated by:** [DYNAMIC_CAPABILITIES_CHANGED][9] notification

### HUMIDITY_STATE
Current humidity state.

**Variable ID:** 1141
**Type:** string
**Read Only:** true
**Hidden:** false
**Updated by:** [HUMIDITY_STATE_CHANGED][15] and [FORCE_INFO][7] notifications

### HVAC_MODE
Current HVAC mode.

**Variable ID:** 1104
**Type:** string
**Read Only:** true
**Hidden:** false
**Updated by:** [HVAC_MODE_CHANGED][22], [ALLOWED_HVAC_MODES_CHANGED][23], and [FORCE_INFO][7] notifications

### HVAC_MODES_LIST
Comma-separated list of supported HVAC modes.

**Variable ID:** 1120
**Type:** string
**Read Only:** true
**Hidden:** true
**Updated by:** [ALLOWED_HVAC_MODES_CHANGED][23] notification

### HVAC_STATE
Current HVAC state.

**Variable ID:** 1107
**Type:** string
**Read Only:** true
**Hidden:** false
**Updated by:** [HVAC_STATE_CHANGED][24] and [FORCE_INFO][7] notifications

### IS_CONNECTED
Indicates whether the hardware is online/available.

**Variable ID:** 1112
**Type:** bool
**Read Only:** true
**Hidden:** false
**Updated by:** [CONNECTION][25] notification

### LOCK_SCREEN_MODE
Current lock screen mode.

**Variable ID:** 1151
**Type:** string
**Read Only:** true
**Hidden:** false
**Updated by:** [LOCK_SCREEN_MODE_CHANGED][26] notification

### MESSAGE
Status message supplied by the protocol driver.

**Variable ID:** 1145
**Type:** string
**Read Only:** true
**Hidden:** false
**Updated by:** [MESSAGE_CHANGED][27] notification

### OUTDOOR_TEMPERATURE_C
Outdoor temperature in Celsius.

**Variable ID:** 1137
**Type:** float
**Read Only:** true
**Hidden:** false
**Updated by:** [OUTDOOR_TEMPERATURE_CHANGED][28] and [FORCE_INFO][7] notifications

### OUTDOOR_TEMPERATURE_F
Outdoor temperature in Fahrenheit.

**Variable ID:** 1136
**Type:** float
**Read Only:** true
**Hidden:** false
**Updated by:** [OUTDOOR_TEMPERATURE_CHANGED][28] and [FORCE_INFO][7] notifications

### PRESET
Currently active preset name.

**Variable ID:** 1144
**Type:** string
**Read Only:** true
**Hidden:** false
**Updated by:** [PRESET_CHANGED][29] notification

### SCALE
Current scale passed in on the `SCALE_CHANGED` notify.

**Variable ID:** 1100
**Type:** string
**Read Only:** true
**Hidden:** false
**Updated by:** [SCALE_CHANGED][32] and [FORCE_INFO][7] notifications

### SINGLE_SETPOINT_C
Current single setpoint in Celsius.

**Variable ID:** 1150
**Type:** float
**Read Only:** false
**Hidden:** false
**Updated by:** [SINGLE_SETPOINT_CHANGED][35] and [FORCE_INFO][7] notifications

### SINGLE_SETPOINT_F
Current single setpoint in Fahrenheit.

**Variable ID:** 1149
**Type:** float
**Read Only:** false
**Hidden:** false
**Updated by:** [SINGLE_SETPOINT_CHANGED][35] and [FORCE_INFO][7] notifications

### TEMPERATURE
Current indoor temperature in the active scale.

**Variable ID:** 1101
**Type:** int
**Read Only:** true
**Hidden:** true
**Updated by:** [TEMPERATURE_CHANGED][5] and [FORCE_INFO][7] notifications

### TEMPERATURE_C
Current temperature in Celsius.

**Variable ID:** 1131
**Type:** float
**Read Only:** true
**Hidden:** false
**Updated by:** [TEMPERATURE_CHANGED][5] notification

### TEMPERATURE_F
Current temperature in Fahrenheit.

**Variable ID:** 1130
**Type:** float
**Read Only:** true
**Hidden:** false
**Updated by:** [TEMPERATURE_CHANGED][5] notification

### VACATION_COOL_SETPOINT
Vacation cool setpoint.

**Variable ID:** 1111
**Type:** int
**Read Only:** false
**Hidden:** false
**Updated by:** [VACATION_SETPOINTS][36] notification

### VACATION_HEAT_SETPOINT
Vacation heat setpoint.

**Variable ID:** 1110
**Type:** int
**Read Only:** false
**Hidden:** false
**Updated by:** [VACATION_SETPOINTS][36] notification

### VACATION_MODE
Vacation mode state.

**Variable ID:** 1109
**Type:** bool
**Read Only:** false
**Hidden:** false
**Updated by:** [VACATION_MODE][37] notification



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-cool_setpoint_changed
[2]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-fan_mode_changed
[3]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-dehumidify_setpoint_change
[4]:  https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-heat_setpoint_changed
[5]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-temperature_changed
[6]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-allowed_fan_modes-_changed
[7]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-force_info
[8]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-fan_state_change
[9]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-dynamic_capabilities_changed
[10]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-hold_mode_changed
[11]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-humidify_setpoint_changed
[12]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-humidity_changed
[13]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-humidity_mode_changed
[14]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-allowed_humidity_modes_changed
[15]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-humidity_state_changed
[20]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-heat_pump_mode
[21]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-allowed_hold_modes_changed
[22]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-hvac_mode_changed
[23]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-allowed_hvac_modes_changed
[24]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-hvac_state_changed
[25]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-connection
[26]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-lock_screen_mode_changed
[27]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-message_changed
[28]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-outdoor_temperature_changed
[29]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-preset_changed
[31]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-reversing_valve
[32]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-scale_changed
[34]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-schedule_entry_changed
[35]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-single_setpoint_changed
[36]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-vacation_setpoints
[37]: https://snap-one.github.io/docs-driverworks-proxyprotocol-tstat/#thermostat-notifications-vacation_mode

