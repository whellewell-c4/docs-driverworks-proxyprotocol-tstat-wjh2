## LOCK_SCREEN_MODES

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string value used to update the list of supported lock screen modes. The value is passed through the payload as text, and it updates the corresponding [`lock_screen_modes`][2] capability. If the parameter is not provided, the default is `date,time`.

### Name

`LOCK_SCREEN_MODES ()`

| Parameter         | Type   | Default | Capability               | Description                          |
| ----------------- | ------ | ------- | ------------------------ | ------------------------------------ |
| LOCK_SCREEN_MODES | STRING | ""      | [`lock_screen_modes`][2] | List of supported lock screen modes. |

### Lua example
```lua
local LockScreenModes = "Unlocked,Partially Locked,Fully Locked"

local Params = {
    LOCK_SCREEN_MODES = LockScreenModes
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities

