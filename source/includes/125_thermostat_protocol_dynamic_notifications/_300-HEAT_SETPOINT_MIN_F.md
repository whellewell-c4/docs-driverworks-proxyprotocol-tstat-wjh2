## HEAT_SETPOINT_MIN_F

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based decimal value used to update the minimum heat setpoint in Fahrenheit. The value must be expressed as a string so it can be passed through the proxy notification payload format. If the parameter is not provided, the default is `0`.

### Name

`HEAT_SETPOINT_MIN_F ()`

| Parameter           | Type | Default | Capability                 | Range                                  | Description                          |
| ------------------- | ---- | ------- | -------------------------- | -------------------------------------- | ------------------------------------ |
| HEAT_SETPOINT_MIN_F | INT  | 31      | [`setpoint_heat_min_f`][2] | 0-100 and < [`setpoint_heat_max_f`][2] | Minimum heat setpoint in Fahrenheit. |

### Lua example
```lua
local HeatSetpointMinF = 40.0

local Params = {
    HEAT_SETPOINT_MIN_F = tostring(HeatSetpointMinF)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
