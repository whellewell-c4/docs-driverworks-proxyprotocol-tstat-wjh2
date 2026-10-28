## HEAT_SETPOINT_MAX_C

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the maximum heat setpoint in Celsius. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`setpoint_heat_max_c`][2] capability. If the parameter is not provided, the default is `100`.

### Name

`HEAT_SETPOINT_MAX_C ()`

| Parameter           | Type | Default | Capability                 | Range                                  | Description                       |
| ------------------- | ---- | ------- | -------------------------- | -------------------------------------- | --------------------------------- |
| HEAT_SETPOINT_MAX_C | INT  | 31      | [`setpoint_heat_max_c`][2] | 0-100 and < [`setpoint_heat_min_c`][2] | Maximum heat setpoint in Celsius. |

### Lua example
```lua
local HeatSetpointMaxC = 32

local Params = {
    HEAT_SETPOINT_MAX_C = tostring(HeatSetpointMaxC)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
