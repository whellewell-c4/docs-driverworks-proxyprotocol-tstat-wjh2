
## HAS_SCHEDULE

Introduced is OS Version 4.3.0. An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based Boolean value (`True`/`False`) used to enable or disable the [`has_schedule`][2] capability. When set to `True`, the device reports that a schedule is supported and the proxy should create or restore schedule state. When set to `False`, the schedule capability is disabled and the schedule is removed. If the parameter is not provided, the default is `False`.

### Name

`HAS_SCHEDULE ()`

| Parameter    | Type | Default | Capability          | Description                                 |
| ------------ | ---- | ------- | ------------------- | ------------------------------------------- |
| HAS_SCHEDULE | BOOL | False   | [`has_schedule`][2] | True/False. Thermostat supports a schedule. |

### Lua example
```lua
local HasSchedule = true

local Params = {
    HAS_SCHEDULE = tostring(HasSchedule)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
