## HUMIDITY_SETPOINT_MIN

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the minimum humidify setpoint. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`setpoint_humidify_min`][2] capability. If the parameter is not provided, the default is `0`.

### Name

`HUMIDITY_SETPOINT_MIN ()`

| Parameter             | Type | Default | Capability                   | Range | Description                |
| --------------------- | ---- | ------- | ---------------------------- | ----- | -------------------------- |
| HUMIDITY_SETPOINT_MIN | INT  | 0       | [`setpoint_humidify_min`][2] | 0-100 | Minimum humidify setpoint. |

### Lua example
```lua
local HumidifySetpointMin = 30

local Params = {
    HUMIDITY_SETPOINT_MIN = tostring(HumidifySetpointMin)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
