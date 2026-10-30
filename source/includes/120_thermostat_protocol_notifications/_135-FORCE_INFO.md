## FORCE_INFO

A no-payload trigger that tells the thermostat proxy to refresh the current UI state from its internal values. When a proxy receives a `FORCE_INFO` notification, it re-sends the current scale, temperature, HVAC mode, fan mode, hold mode, HVAC state, fan state, and heat/cool setpoints back to the UI so the display stays synchronized without requiring a separate variable-specific notification.

### Name

`FORCE_INFO ()`

| Parameter | Type | Default | Capability | Description |
| --------- | ---- | ------- | ---------- | ----------- |
| none | None | N/A | N/A | This notification has no payload. It forces the proxy to refresh current information back to the UI. |

### Lua example
```lua
local Params = {}

C4:SendToProxy(bindingID, "FORCE_INFO", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("FORCE_INFO", Params, BindingID)
```

### What this refreshes

The proxy uses `FORCE_INFO` to push the most recent values for the following items back to the UI:

- scale
- current temperature
- HVAC mode
- fan mode
- hold mode
- HVAC state
- fan state
- heat setpoint
- cool setpoint
- display temperature values

This is a refresh trigger, not a state-change command. It does not require any parameters and does not update the target device; it simply re-sends the current data from the proxy to the UI.
