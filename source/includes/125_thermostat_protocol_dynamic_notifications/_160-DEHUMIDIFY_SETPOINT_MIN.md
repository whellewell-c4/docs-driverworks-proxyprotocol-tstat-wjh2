## DEHUMIDIFY_SETPOINT_MIN

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the minimum dehumidify setpoint. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`setpoint_dehumidify_min`][2] capability. If the parameter is not provided, the default is `0`.

### Name

`DEHUMIDIFY_SETPOINT_MIN ()`

| Parameter               | Type | Default | Capability                     | Range | Description                  |
| ----------------------- | ---- | ------- | ------------------------------ | ----- | ---------------------------- |
| DEHUMIDIFY_SETPOINT_MIN | INT  | 0       | [`setpoint_dehumidify_min`][2] | 0-100 | Minimum dehumidify setpoint. |

### Lua example
```lua
local DehumidifySetpointMin = 30

local Params = {
    DEHUMIDIFY_SETPOINT_MIN = tostring(DehumidifySetpointMin)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
