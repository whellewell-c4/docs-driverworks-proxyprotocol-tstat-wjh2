## SINGLE_SETPOINT_RESOLUTION_F

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the single setpoint resolution in Fahrenheit. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`setpoint_single_resolution_f`][2] capability. If the parameter is not provided, the default is `1`.

### Name

`SINGLE_SETPOINT_RESOLUTION_F ()`

| Parameter                    | Type | Default | Capability                          | Description                               |
| ---------------------------- | ---- | ------- | ----------------------------------- | ----------------------------------------- |
| SINGLE_SETPOINT_RESOLUTION_F | INT  | 1       | [`setpoint_single_resolution_f`][2] | Single setpoint resolution in Fahrenheit. |

### Lua example
```lua
local SingleSetpointResolutionF = 1

local Params = {
    SINGLE_SETPOINT_RESOLUTION_F = tostring(SingleSetpointResolutionF)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
