## OUTDOOR_TEMPERATURE_RESOLUTION_C

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the outdoor temperature resolution in Celsius. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`outdoor_temperature_resolution_c`][2] capability. If the parameter is not provided, the default is `1`.

### Name

`OUTDOOR_TEMPERATURE_RESOLUTION_C ()`

| Parameter                        | Type | Default | Capability                              | Description                                |
| -------------------------------- | ---- | ------- | --------------------------------------- | ------------------------------------------ |
| OUTDOOR_TEMPERATURE_RESOLUTION_C | INT  | 1       | [`outdoor_temperature_resolution_c`][2] | Outdoor temperature resolution in Celsius. |

### Lua example
```lua
local OutdoorTemperatureResolutionC = .5

local Params = {
    OUTDOOR_TEMPERATURE_RESOLUTION_C = tostring(OutdoorTemperatureResolutionC)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
