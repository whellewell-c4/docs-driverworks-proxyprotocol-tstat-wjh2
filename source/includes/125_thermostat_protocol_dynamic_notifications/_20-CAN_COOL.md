## CAN\_COOL

An optional  parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based Boolean value (`True`/`False`) used to enable or disable the [`can_cool`][2] capability. When set to `True`, the device reports that Cool mode is supported; when set to `False`, the capability is disabled. If the parameter is not provided, the default is `False`.


### Name

`CAN_COOL ()`


| Parameter | Type | Default | Capability      | Description                              |
| --------- | ---- | ------- | --------------- | ---------------------------------------- |
| CAN_COOL  | BOOL | False   | [`can_cool`][2] | True/False. Thermostat supports cooling. |


### Lua example
```lua
local CanCool = true

local Params = {
    CAN_COOL = tostring(CanCool)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities

