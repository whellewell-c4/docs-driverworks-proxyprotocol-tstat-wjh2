## HAS_OUTDOOR_TEMPERATURE

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based Boolean value (`True`/`False`) used to enable or disable the [`has_outdoor_temperature`][2] capability. When set to `True`, the thermostat supports and exposes outdoor temperature data; when set to `False`, the capability is disabled. If the parameter is not provided, the default is `False`.

### Name

`HAS_OUTDOOR_TEMPERATURE ()`

| Parameter | Type | Default | Capability | Description |
| --------- | ---- | ------- | ---------- | ----------- |
| HAS_OUTDOOR_TEMPERATURE | BOOL | False | [`has_outdoor_temperature`][2] | True/False. Thermostat exposes outdoor temperature. |

### Lua example
```lua
local HasOutdoorTemperature = true

local Params = {
    HAS_OUTDOOR_TEMPERATURE = tostring(HasOutdoorTemperature)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
