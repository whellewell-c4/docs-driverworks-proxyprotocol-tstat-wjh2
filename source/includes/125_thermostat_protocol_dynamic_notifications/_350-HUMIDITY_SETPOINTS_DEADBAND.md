## HUMIDITY_SETPOINT_DEADBAND

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the humitity setpoint deadband. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`setpoint_humidity_deadband`][2] capability. If the parameter is not provided, the default is `10`.

### Name

`HUMIDITY_SETPOINT_DEADBAND ()`

| Parameter                  | Type | Default | Capability                        | Range | Description                                           |
| -------------------------- | ---- | ------- | --------------------------------- | ----- | ----------------------------------------------------- |
| HUMIDITY_SETPOINT_DEADBAND | INT  | 10      | [`setpoint_humidity_deadband`][2] |       | What the deadband between humidify and dehumidify is. |

### Lua example
```lua
local HeatCoolSetpointsDeadbandC = 2

local Params = {
    HUMIDITY_SETPOINT_DEADBAND = tostring(HeatCoolSetpointsDeadbandC)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
