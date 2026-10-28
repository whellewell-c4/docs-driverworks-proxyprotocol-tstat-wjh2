## HAS_EXTRAS

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based Boolean value (`True`/`False`) used to enable or disable the [`has_extras`][2] capability. When set to `True`, the driver needs to provide the `<extras>` XML containing the definition of all the `Extras` needed by the UI. This is provided by the [`EXTRAS_SETUP_CHANGED`][3] notification.  extra the  exposes the thermostat features; when set to `False`, the capability is disabled and the driver does not provide any `Extras`. If the parameter is not provided, the default is `False`.

### Name

`HAS_EXTRAS ()`

| Parameter | Type | Default | Capability | Description |
| --------- | ---- | ------- | ---------- | ----------- |
| HAS_EXTRAS | BOOL | False | [`has_extras`][2] | True/False. Thermostat exposes "Extras" feature. |

### Lua example
```lua
local HasExtras = true

local Params = {
    HAS_EXTRAS = tostring(HasExtras)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
[3]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-extras_setup_changed
