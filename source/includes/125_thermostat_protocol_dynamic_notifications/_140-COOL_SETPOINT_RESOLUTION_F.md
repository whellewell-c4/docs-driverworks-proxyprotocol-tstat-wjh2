## COOL_SETPOINT_RESOLUTION_F

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the cool setpoint resolution in Fahrenheit. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`setpoint_cool_resolution_f`][2] capability. If the parameter is not provided, the default is `1`.

### Name

`COOL_SETPOINT_RESOLUTION_F ()`

| Parameter                  | Type | Default | Capability                        | Range    | Description                                               |
| -------------------------- | ---- | ------- | --------------------------------- | -------- | --------------------------------------------------------- |
| COOL_SETPOINT_RESOLUTION_F | INT  | 1       | [`setpoint_cool_resolution_f`][2] | 0.01-100 | Cool setpoint resolution in Fahrenheit (ie 1,3,5,10,etc). |

### Lua example
```lua
local CoolSetpointResolutionF = .5

local Params = {
    COOL_SETPOINT_RESOLUTION_F = tostring(CoolSetpointResolutionF)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
