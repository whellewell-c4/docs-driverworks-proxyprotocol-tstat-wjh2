## DEHUMIDIFY_SETPOINT_RESOLUTION

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the dehumidify setpoint resolution. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`setpoint_dehumidify_resolution`][2] capability. If the parameter is not provided, the default is `1`.

### Name

`DEHUMIDIFY_SETPOINT_RESOLUTION ()`

| Parameter                      | Type | Default | Capability                            | Range | Description                     |
| ------------------------------ | ---- | ------- | ------------------------------------- | ----- | ------------------------------- |
| DEHUMIDIFY_SETPOINT_RESOLUTION | INT  | 1       | [`setpoint_dehumidify_resolution`][2] | 0-100 | Dehumidify setpoint resolution. |

### Lua example
```lua
local DehumidifySetpointResolution = 5

local Params = {
    DEHUMIDIFY_SETPOINT_RESOLUTION = tostring(DehumidifySetpointResolution)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
