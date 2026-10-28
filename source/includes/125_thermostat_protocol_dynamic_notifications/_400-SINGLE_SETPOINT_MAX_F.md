## SINGLE_SETPOINT_MAX_F

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the maximum single setpoint in Fahrenheit. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`setpoint_single_max_f`][2] capability. If the parameter is not provided, the default is `90`.

### Name

`SINGLE_SETPOINT_MAX_F ()`

| Parameter             | Type | Default | Capability                   | Range                                    | Description                            |
| --------------------- | ---- | ------- | ---------------------------- | ---------------------------------------- | -------------------------------------- |
| SINGLE_SETPOINT_MAX_F | INT  | 90      | [`setpoint_single_max_f`][2] | 0-100 and < [`setpoint_single_min_f`][2] | Maximum single setpoint in Fahrenheit. |

### Lua example
```lua
local SingleSetpointMaxF = 90

local Params = {
    SINGLE_SETPOINT_MAX_F = tostring(SingleSetpointMaxF)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
