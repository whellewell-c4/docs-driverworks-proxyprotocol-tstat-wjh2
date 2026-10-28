## HEATCOOL_SETPOINTS_DEADBAND_C

An optional parameter included in a [`DYNAMIC_CAPABILITIES_CHANGED`][1] notification received by the proxy via a `C4:SendToProxy` call. It is a string-based integer value used to update the heat/cool deadband in Celsius. The value is passed through the payload as a string representation of the number and is applied to the corresponding [`setpoint_heatcool_deadband_c`][2] capability. If the parameter is not provided, the default is `2`.

### Name

`HEATCOOL_SETPOINTS_DEADBAND_C ()`

| Parameter | Type | Default | Capability | Range | Description |
| --------- | ---- | ------- | ---------- | ----- | ----------- |
| HEATCOOL_SETPOINTS_DEADBAND_C | INT | 2 | [`setpoint_heatcool_deadband_c`][2] |  | Heat/cool deadband in Celsius. |

### Lua example
```lua
local HeatCoolSetpointsDeadbandC = 2

local Params = {
    HEATCOOL_SETPOINTS_DEADBAND_C = tostring(HeatCoolSetpointsDeadbandC)
}

C4:SendToProxy(bindingID, "DYNAMIC_CAPABILITIES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("DYNAMIC_CAPABILITIES_CHANGED", Params, BindingID)
```



[1]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]: https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-capabilities
