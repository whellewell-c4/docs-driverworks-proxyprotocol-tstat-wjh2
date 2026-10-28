## TEMPERATURE_MIN_F

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the minimum current temperature in Fahrenheit. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`current_temperature_min_f`][2] capability. If the parameter is not provided, the default is `-40`.

### Name

`TEMPERATURE_MIN_F ()`

| Parameter         | Type | Default | Capability                       | Description                                |
| ----------------- | ---- | ------- | -------------------------------- | ------------------------------------------ |
| TEMPERATURE_MIN_F | INT  | -40     | [`current_temperature_min_f`][2] | Minimum current temperature in Fahrenheit. |

### Lua example
```lua
local TemperatureMinF = -40

local Params = {
    TEMPERATURE_MIN_F = tostring(TemperatureMinF)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
