## DYNAMIC\_CAPABILITIES\_CHANGED

Dynamic Capabilities is a way for a protocol driver to send updates about some thermostat capabilities that can be changed when settings change on the hardware.  An example would be a thermostat that has a humidifier added would need to tell the proxy it can now do humidification as well as what the min, max, resolution and other changes are for the setpoint. 

Note the following is an example of the notification. For a complete list of Thermostat capabilities that can be passed as parameters, please see the [Thermostat Proxy Capabilities][1] section.

### Name

`DYNAMIC_CAPABILITIES_CHANGED ()`


| Parameter                      | Type | Description                                                                                                                             |
| ------------------------------ | ---- | --------------------------------------------------------------------------------------------------------------------------------------- |
|                                |      |                                                                                                                                         |
|                                |      |                                                                                                                                         |
| `HAS_HUMIDITY`                 | BOOL | boolean to enable/disable [`has_humidity`][2] capability, if the device supports this feature, default is false.                        |
|                                |      |                                                                                                                                         |
| `HUMIDIFY_SETPOINT_MIN`        | INT  | Minimum Setpoint, int 0-100 that will do the same thing as the [`setpoint_humidify_min`][3] capability, default 0                       |
| `HUMIDIFY_SETPOINT_MAX`        | INT  | Minimum Setpoint, int 0-100 that will do the same thing as the [`setpoint_humidify_max`][4] capability, default 100                     |
| `HUMIDIFY_SETPOINT_RESOLUTION` | INT  | What increment to use (ie 1,3,5,10,etc), will do the same thing as the `setpoint_humidify_resolution` capability, default 1             |
| `HUMIDITY_SETPOINT_DEADBAND`   | INT  | What the deadband between humidify and dehumidify is, will do the same thing as the `setpoint_humidity_deadband` capability, default 10 |
| `DEHUMIDIFY_SETPOINT_MIN`:     | INT  | Minimum Setpoint, int 0-100 that will do the same thing as the `setpoint_dehumidify_min` capability, default 0                          |


### Returns

`None`


[1]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
[2]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
[3]:	hhttps://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
[4]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities