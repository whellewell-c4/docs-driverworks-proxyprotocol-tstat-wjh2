### Name

`SCHEDULE_ENTRY_DELETED` This notification is new in 4.3.0.

### Parameters

|Name|Type|Description|
|---|---|---|
|`ENTRY_INDEX`|INTEGER|Required. The schedule entry index to delete.|
|`DAY_INDEX`|INTEGER|Optional. The day index to target. If omitted, the delete is applied across all days.|

### Updated variables

- `EntireSchedule` (ID = 1113)

### Lua example

```lua
local Params = {
    ENTRY_INDEX = "2",
    DAY_INDEX = "0"
}

SendNotify("SCHEDULE_ENTRY_DELETED", Params, BindingID)
```


### Returns

None.

This notification is new in 4.3.0. If a specific `DAY_INDEX` is provided, the handler deletes that one schedule entry for that day; otherwise, it applies the delete across all days. After the update, it refreshes the affected schedule data and sends the updated schedule to the UI.