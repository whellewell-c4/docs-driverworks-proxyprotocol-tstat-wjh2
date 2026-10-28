## COOL_SETPOINT_MAX_F

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the maximum cool setpoint in Fahrenheit. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`setpoint_cool_max_f`][2] capability. If the parameter is not provided, the default is `90`.

### Name

`COOL_SETPOINT_MAX_F ()`

| Parameter           | Type | Default | Capability                 | Range                                  | Description                          |
| ------------------- | ---- | ------- | -------------------------- | -------------------------------------- | ------------------------------------ |
| COOL_SETPOINT_MAX_F | INT  | 90      | [`setpoint_cool_max_f`][2] | 0-100 and < [`setpoint_cool_min_f`][2] | Maximum cool setpoint in Fahrenheit. |

### Lua example
```lua
local CoolSetpointMaxF = 90

local Params = {
    COOL_SETPOINT_MAX_F = tostring(CoolSetpointMaxF)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
