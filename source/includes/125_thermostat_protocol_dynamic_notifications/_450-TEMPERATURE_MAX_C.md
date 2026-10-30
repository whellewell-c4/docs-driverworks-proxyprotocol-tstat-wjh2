## TEMPERATURE_MAX_C

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the maximum current temperature in Celsius. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`current_temperature_max_c`][2] capability. If the parameter is not provided, the default is `50`.

### Name

`TEMPERATURE_MAX_C ()`

| Parameter         | Type | Default | Capability                       | Range | Description                             |
| ----------------- | ---- | ------- | -------------------------------- | ----- | --------------------------------------- |
| TEMPERATURE_MAX_C | INT  | 50      | [`current_temperature_max_c`][2] |       | Maximum current temperature in Celsius. |

### Lua example
```lua
local TemperatureMaxC = 50

local Params = {
    TEMPERATURE_MAX_C = tostring(TemperatureMaxC)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
