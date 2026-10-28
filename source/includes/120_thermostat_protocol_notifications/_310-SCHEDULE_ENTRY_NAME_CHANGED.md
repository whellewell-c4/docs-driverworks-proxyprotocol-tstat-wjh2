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
local entryIndex = 2
local dayIndex = 1

local Params = {
	ENTRY_INDEX = tostring(entryIndex),
    DAY_INDEX = tostring(dayIndex),
	ENTRY_NAME = tostring("Wake")
}

C4:SendToProxy(bindingID, "SCHEDULE_ENTRY_NAME_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("SCHEDULE_ENTRY_NAME_CHANGED", Params, BindingID)
```

When `DAY_INDEX` is omitted:

```lua
local entryIndex = 2
local dayIndex = 1

local Params = {
	ENTRY_INDEX = tostring(entryIndex),
	ENTRY_NAME = tostring("Wake")
}

C4:SendToProxy(bindingID, "SCHEDULE_ENTRY_NAME_CHANGED", Params, "NOTIFY")

-- if using the template code you can use SendNotify
--SendNotify("SCHEDULE_ENTRY_NAME_CHANGED", Params, BindingID)
```


This applies the rename to the same entry index on every day of the schedule.


### Returns

`None`