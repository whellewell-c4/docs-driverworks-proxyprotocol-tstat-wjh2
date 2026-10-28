## HAS_HUMIDITY

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based Boolean value (`True`/`False`) used to enable or disable the [`has_humidity`][2] capability. When set to `True`, the thermostat exposes humidity values; when set to `False`, the capability is disabled. If the parameter is not provided, the default is `False`.

### Name

`HAS_HUMIDITY ()`

| Parameter | Type | Default | Capability | Description |
| --------- | ---- | ------- | ---------- | ----------- |
| HAS_HUMIDITY | BOOL | False | [`has_humidity`][2] | True/False. Thermostat exposes humidity data. |

### Lua example
```lua
local HasHumidity = true

local Params = {
    HAS_HUMIDITY = tostring(HasHumidity)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
