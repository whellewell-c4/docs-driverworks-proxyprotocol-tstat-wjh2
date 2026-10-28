## TEMPERATURE_RESOLUTION_F

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the current temperature resolution in Fahrenheit. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`current_temperature_resolution_f`][2] capability. If the parameter is not provided, the default is `1`.

### Name

`TEMPERATURE_RESOLUTION_F ()`

| Parameter                | Type | Default | Capability                              | Description                                   |
| ------------------------ | ---- | ------- | --------------------------------------- | --------------------------------------------- |
| TEMPERATURE_RESOLUTION_F | INT  | 1       | [`current_temperature_resolution_f`][2] | Current temperature resolution in Fahrenheit. |

### Lua example
```lua
local TemperatureResolutionF = 1

local Params = {
    TEMPERATURE_RESOLUTION_F = tostring(TemperatureResolutionF)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
