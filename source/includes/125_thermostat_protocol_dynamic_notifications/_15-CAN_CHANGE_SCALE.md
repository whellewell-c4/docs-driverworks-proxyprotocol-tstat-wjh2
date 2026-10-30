## CAN\_CHANGE\_SCALE

An optional  parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based Boolean value (`True`/`False`) used to enable or disable the [`can_change_scare`][2] capability. When set to `True`, the device reports that the ability to Change Scale is supported; when set to `False`, the capability is disabled. If the parameter is not provided, the default is `False`.


### Name

`CAN_CHANGE_SCALE ()`


| Parameter        | Type | Default | Capability              | Description                                              |
| ---------------- | ---- | ------- | ----------------------- | -------------------------------------------------------- |
| CAN_CHANGE_SCALE | BOOL | False   | [`can_change_scale`][2] | True/False. Thermostat supports ability to change scale. |


### Lua example
```lua
local CanChangeScale = true

local Params = {
    CAN_CHANGE_SCALE = tostring(CanChangeScale)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities


