## ALLOWED_HOLD_MODES_CHANGED

Updates the available hold modes for the thermostat.


### Name

`ALLOWED_HOLD_MODES_CHANGED`


### Parameters

| Name    | Type | Description                                               |
| ------- | ---- | --------------------------------------------------------- |
| `MODES` | LIST | Required. A comma-delimited list of available hold modes. |


### Updated variables

- `HoldModes` (ID = 1122)
- `HoldMode` (ID = 1106)


### Lua example

```lua
local ModesStr = "Next Period,Hold Until,Permanently,Remove Hold"
local Params = {
    MODES = tostring(ModesStr)
}

SendNotify("ALLOWED_HOLD_MODES_CHANGED", Params, BindingID)
```


### Returns

None.
