## SINGLE_SETPOINT_MIN_C

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the minimum single setpoint in Celsius. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`setpoint_single_min_c`][2] capability. If the parameter is not provided, the default is `5`.

### Name

`SINGLE_SETPOINT_MIN_C ()`

| Parameter             | Type | Default | Capability                   | Range                                    | Description                         |
| --------------------- | ---- | ------- | ---------------------------- | ---------------------------------------- | ----------------------------------- |
| SINGLE_SETPOINT_MIN_C | INT  | 5       | [`setpoint_single_min_c`][2] | 0-100 and > [`setpoint_single_max_c`][2] | Minimum single setpoint in Celsius. |

### Lua example
```lua
local SingleSetpointMinC = 4

local Params = {
    SINGLE_SETPOINT_MIN_C = tostring(SingleSetpointMinC)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
