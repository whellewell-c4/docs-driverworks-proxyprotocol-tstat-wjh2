## ALLOWED\_FAN\_MODES \_CHANGED

Updates the allowed fan mode list for the thermostat.


### Name

`ALLOWED_FAN_MODES_CHANGED ()`


### Parameters

| Name    | Type | Description                                              |
| ------- | ---- | -------------------------------------------------------- |
| `Modes` | LIST | Required. A comma-delimited list of available fan modes. |


### Updated variables

- `FanModes` (ID = 1121)
- `FanMode` (ID = 1105)


### Lua example

```lua
local ModesStr = "On,Auto,Circulate,Schedule,Low,Medium,High"
local Params = {
    MODES = tostring(ModesStr)
}

C4:SendToProxy(bindingID, "ALLOWED_FAN_MODES_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("ALLOWED_FAN_MODES_CHANGED", Params, BindingID)
```


### Returns

`None`


