## HAS_HEAT_PUMP

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based Boolean value (`True`/`False`) used to enable or disable the [`has_heat_pump`][2] capability. When set to `True`, the thermostat is configured as a heat pump system; when set to `False`, the capability is disabled. If the parameter is not provided, the default is `False`.

### Name

`HAS_HEAT_PUMP ()`

| Parameter | Type | Default | Capability | Description |
| --------- | ---- | ------- | ---------- | ----------- |
| HAS_HEAT_PUMP | BOOL | False | [`has_heat_pump`][2] | True/False. Thermostat is configured as a heat pump. |

### Lua example
```lua
local HasHeatPump = true

local Params = {
    HAS_HEAT_PUMP = tostring(HasHeatPump)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
