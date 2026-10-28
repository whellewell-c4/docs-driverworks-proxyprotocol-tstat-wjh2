## TEMPERATURE_MAX_F

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the maximum current temperature in Fahrenheit. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`current_temperature_max_f`][2] capability. If the parameter is not provided, the default is `120`.

### Name

`TEMPERATURE_MAX_F ()`

| Parameter         | Type | Default | Capability                       | Description                                |
| ----------------- | ---- | ------- | -------------------------------- | ------------------------------------------ |
| TEMPERATURE_MAX_F | INT  | 120     | [`current_temperature_max_f`][2] | Maximum current temperature in Fahrenheit. |

### Lua example
```lua
local TemperatureMaxF = 120

local Params = {
    TEMPERATURE_MAX_F = tostring(TemperatureMaxF)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
