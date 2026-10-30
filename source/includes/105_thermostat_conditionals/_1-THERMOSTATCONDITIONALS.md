## THERMOSTAT CONDITIONALS

The following Conditionals are supported with the Thermostat Proxy and can be used in ComposerPro Programming. Please see the Samples folder delivered in this SDK for Thermostat (V2) code examples.

- `IF_COOL_SETPOINT` - simple integer test against the current cool setpoint.

- `IF_FAN_MODE` - simple boolean test to see if the fan is in a given mode.

- `IF_FAN_STATE` - simple boolean test to see if the fan is in a given state.

- `IF_HEAT_SETPOINT` - simple integer test against the current heat setpoint.

- `IF_HOLD_MODE` - simple boolean test to see if the hold mode is in a given mode.

- `IF_HUMIDIFY_SETPOINT` - simple integer test on an int number to see if the current humidify setpoint is a supplied value.

- `IF_HUMIDITY` - numeric comparison against the current humidity value.

- `IF_HUMIDITY_MODE` - simple boolean test on a string to see if the humidity mode is in a given mode.

- `IF_HUMIDITY_STATE` - simple boolean test on a string to see if the humidity state is in a given mode.

- `IF_HVAC_MODE` - simple boolean test to see if the HVAC is in a given mode.

- `IF_HVAC_STATE` - simple boolean test to see if the HVAC is in a given state.

- `IF_DEHUMIDIFY_SETPOINT` - numeric comparison against the current dehumidify setpoint.

- `IF_OUTDOOR_TEMPERATURE` - simple integer test to see if the current temperature is a supplied value. No manipulation is done on the units for the temperature. If the thermostat is configured to be Celsius, the value to compare it with should be in Celsius as well.

- `IF_PRESET` - simple boolean test to see if the preset is in a given name.

- `IF_SINGLE_SETPOINT` - numeric comparison against the current single setpoint.

- `IF_TEMPERATURE` - simple integer test to see if the current temperature is a supplied value. No manipulation is done on the units for the temperature. If the thermostat is configured to be celsius, the value to compare it with should be in Celsius as well.

- `IF_VACATION_MODE` - simple boolean test to see if the vacation mode is on/off.
