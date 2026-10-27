
## LOCK_SCREEN_MODE_CHANGED

Updates the current lock screen mode.  This notification is new in 4.3.0.


### Name

`LOCK_SCREEN_MODE_CHANGED`


### Parameters

| Name   | Type   | Description                                                                                   |
| ------ | ------ | --------------------------------------------------------------------------------------------- |
| `MODE` | STRING | Required. The new lock screen mode value. Modes come from the `lock_screen_modes` capability. |


### Updated variables

- `LockScreenMode` (ID = 1151)


### Lua example

```lua
local Params = {
    MODE = "Partially Locked"
}

SendNotify("LOCK_SCREEN_MODE_CHANGED", Params, BindingID)
```


### Returns

None.

