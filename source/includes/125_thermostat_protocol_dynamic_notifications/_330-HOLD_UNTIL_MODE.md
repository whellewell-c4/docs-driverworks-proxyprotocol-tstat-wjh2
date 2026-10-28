## HOLD_UNTIL_MODE

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string value used to update the hold-until mode list. The value is passed through the payload as text, and it updates the corresponding [`hold_until_mode`][2] capability. If the parameter is not provided, the default is `date,time`.

### Name

`HOLD_UNTIL_MODE ()`

| Parameter | Type | Default | Capability | Description |
| --------- | ---- | ------- | ---------- | ----------- |
| HOLD_UNTIL_MODE | STRING | date,time | [`hold_until_mode`][2] | Hold-until mode list supported by the thermostat. |

### Lua example
```lua
local HoldUntilMode = "date,time"

local Params = {
    HOLD_UNTIL_MODE = HoldUntilMode
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
