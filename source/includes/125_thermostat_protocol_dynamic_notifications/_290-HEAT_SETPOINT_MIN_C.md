## HEAT_SETPOINT_MIN_C

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based decimal value used to update the minimum heat setpoint in Celsius. The value must be expressed as a string so it can be passed through the proxy notification payload format. If the parameter is not provided, the default is `0`.

### Name

`HEAT_SETPOINT_MIN_C ()`

| Parameter           | Type | Default | Capability                 | Range                                  | Description                       |
| ------------------- | ---- | ------- | -------------------------- | -------------------------------------- | --------------------------------- |
| HEAT_SETPOINT_MIN_C | INT  | 4       | [`setpoint_heat_min_c`][2] | 0-100 and > [`setpoint_heat_max_c`][2] | Minimum heat setpoint in Celsius. |

### Lua example
```lua
local HeatSetpointMinC = 5

local Params = {
    HEAT_SETPOINT_MIN_C = tostring(HeatSetpointMinC)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
