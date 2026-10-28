## HEAT_SETPOINT_MAX_F

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the maximum heat setpoint in Fahrenheit. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`setpoint_heat_max_f`][2] capability. If the parameter is not provided, the default is `100`.

### Name

`HEAT_SETPOINT_MAX_F ()`

| Parameter           | Type | Default | Capability                 | Range                                  | Description                          |
| ------------------- | ---- | ------- | -------------------------- | -------------------------------------- | ------------------------------------ |
| HEAT_SETPOINT_MAX_F | INT  | 89      | [`setpoint_heat_max_f`][2] | 0-100 and < [`setpoint_heat_min_f`][2] | Maximum heat setpoint in Fahrenheit. |

### Lua example
```lua
local HeatSetpointMaxF = 90

local Params = {
    HEAT_SETPOINT_MAX_F = tostring(HeatSetpointMaxF)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
