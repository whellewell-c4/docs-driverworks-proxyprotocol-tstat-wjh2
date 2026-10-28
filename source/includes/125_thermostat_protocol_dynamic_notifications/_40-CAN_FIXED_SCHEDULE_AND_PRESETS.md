An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based Boolean value (`True`/`False`) used to enable or disable the [`can_fixed_schedule_and_presets`][2] capability. When set to `True`, the thermostat supports fixed scheduling with presets; when set to `False`, the capability is disabled. If the parameter is not provided, the default is `False`.

### Name

`CAN_FIXED_SCHEDULE_AND_PRESETS ()`

| Parameter | Type | Default | Capability | Description |
| --------- | ---- | ------- | ---------- | ----------- |
| CAN_FIXED_SCHEDULE_AND_PRESETS | BOOL | False | [`can_fixed_schedule_and_presets`][2] | True/False. Thermostat supports fixed schedule and preset combinations. |

### Lua example
```lua
local CanFixedScheduleAndPresets = true

local Params = {
    CAN_FIXED_SCHEDULE_AND_PRESETS = tostring(CanFixedScheduleAndPresets)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
