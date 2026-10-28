## HAS_TEMPERATURE

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based Boolean value (`True`/`False`) used to enable or disable the [`has_temperature`][2] capability. When set to `True`, the device reports that temperature data is available; when set to `False`, the capability is disabled. If the parameter is not provided, the default is `True`.

### Name

`HAS_TEMPERATURE ()`

| Parameter | Type | Default | Capability | Description |
| --------- | ---- | ------- | ---------- | ----------- |
| HAS_TEMPERATURE | BOOL | True | [`has_temperature`][2] | True/False. Thermostat exposes temperature data. |

### Lua example
```lua
local HasTemperature = true

local Params = {
    HAS_TEMPERATURE = tostring(HasTemperature)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
