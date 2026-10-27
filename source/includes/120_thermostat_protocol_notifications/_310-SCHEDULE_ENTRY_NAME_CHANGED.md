## SCHEDULE_ENTRY_NAME_CHANGED

New in 4.3.0.


### Parameters

- `ENTRY_INDEX` — required. The schedule entry index to rename.
- `ENTRY_NAME` — required. The new name to assign to the schedule entry.
- `DAY_INDEX` — optional. If supplied, only that day’s entry is renamed. If omitted, the same entry index is renamed across all days in the week.


### Updated variables

`None`


### Lua example

```lua
SendNotify("SCHEDULE_ENTRY_NAME_CHANGED", {
    ENTRY_INDEX = "2",
    DAY_INDEX = "1",
    ENTRY_NAME = "Wake"
})
```

When `DAY_INDEX` is omitted:

```lua
SendNotify("SCHEDULE_ENTRY_NAME_CHANGED", {
    ENTRY_INDEX = "2",
    ENTRY_NAME = "Wake"
})
```


This applies the rename to the same entry index on every day of the schedule.


### Returns

`None`