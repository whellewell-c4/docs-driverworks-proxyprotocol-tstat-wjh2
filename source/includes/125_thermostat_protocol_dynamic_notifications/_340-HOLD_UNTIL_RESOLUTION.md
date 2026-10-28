## HOLD_UNTIL_RESOLUTION

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the hold-until resolution. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`hold_until_resolution`][2] capability. If the parameter is not provided, the default is `5`.

### Name

`HOLD_UNTIL_RESOLUTION ()`

| Parameter             | Type | Default | Capability                   | Description                  |
| --------------------- | ---- | ------- | ---------------------------- | ---------------------------- |
| HOLD_UNTIL_RESOLUTION | INT  | 5       | [`hold_until_resolution`][2] | Hold-until resolution value. |

### Lua example
```lua
local HoldUntilResolution = 5

local Params = {
    HOLD_UNTIL_RESOLUTION = tostring(HoldUntilResolution)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
