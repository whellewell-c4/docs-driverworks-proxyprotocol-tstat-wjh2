
## SCHEDULE_ENTRY_RESTORED

New in 4.3.0.

### Parameters

- `ENTRY_INDEX` — required. The schedule entry index to restore.
- `DAY_INDEX` — optional. If supplied, only that day’s entry is restored. If omitted, the same entry index is restored across all days in the week.

### Updated variables

- None directly.
- The handler updates the schedule entry state in memory and refreshes the UI schedule data:
    - `ConSendDataToUI(GetScheduleEntry(entry))` when a single day is targeted
    - `ConSendDataToUI(GetSchedule())` when the restore applies across the week
    - `BC_SendSingleScheduleEntry(entry)` or `BC_SendSchedule()`

### Lua example

```lua
SendNotify("SCHEDULE_ENTRY_RESTORED", {
    ENTRY_INDEX = "2",
    DAY_INDEX = "1"
})
```

When `DAY_INDEX` is omitted:

```lua
SendNotify("SCHEDULE_ENTRY_RESTORED", {
    ENTRY_INDEX = "2"
})
```

This restores the same entry index on every day of the schedule.

### Returns

`None`