## CAN_LOCK_SCREEN

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based Boolean value (`True`/`False`) used to enable or disable the [`can_lock_screen`][2] capability. When set to `True`, the device reports that the Screen on the thermostat device can be locked; when set to `False`, the capability is disabled. If the parameter is not provided, the default is `False`. The modes that are supported are provided by the `<lock_screen_modes>` capability. 

### Name

`CAN_LOCK_SCREEN ()`

| Parameter       | Type | Default | Capability             | Description                                     |
| --------------- | ---- | ------- | ---------------------- | ----------------------------------------------- |
| CAN_LOCK_SCREEN | BOOL | False   | [`can_lock_screen`][2] | True/False. Thermostat supports screen locking. |

### Lua example
```lua
local CanLockScreen = true

local Params = {
    CAN_LOCK_SCREEN = tostring(CanLockScreen)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
