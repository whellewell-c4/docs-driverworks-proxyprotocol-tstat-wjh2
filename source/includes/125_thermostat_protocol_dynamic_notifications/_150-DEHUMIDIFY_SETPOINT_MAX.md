## DEHUMIDIFY_SETPOINT_MAX

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the maximum dehumidify setpoint. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`setpoint_dehumidify_max`][2] capability. If the parameter is not provided, the default is `100`.

### Name

`DEHUMIDIFY_SETPOINT_MAX ()`

| Parameter               | Type | Default | Capability                     | Range | Description                  |
| ----------------------- | ---- | ------- | ------------------------------ | ----- | ---------------------------- |
| DEHUMIDIFY_SETPOINT_MAX | INT  | 100     | [`setpoint_dehumidify_max`][2] | 0-100 | Maximum dehumidify setpoint. |

### Lua example
```lua
local DehumidifySetpointMax = 60

local Params = {
    DEHUMIDIFY_SETPOINT_MAX = tostring(DehumidifySetpointMax)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
