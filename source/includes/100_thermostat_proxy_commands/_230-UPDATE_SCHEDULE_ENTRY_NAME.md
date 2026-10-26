## UPDATE_SCHEDULE_ENTRY_NAME

New in 4.3.0.

### Parameters

- `ENTRY_INDEX` — required; zero-based index of the schedule entry within each day.
- `NEW_NAME` — required; the replacement name to apply to the entry.

### Notes

- This command applies to all days in the week at the specified `ENTRY_INDEX`.
- It does not use `DAY_INDEX`; the proxy loops through every day and updates each matching entry.
- The target index must be valid for the thermostat’s `GetEntriesPerDay()` range.
- Before renaming any day, the proxy validates every day in the week. If any entry at that index is not re-nameable, the command is rejected and no rename is applied.

### Proxy behavior after completion

- The proxy checks that the schedule exists and that `ENTRY_INDEX` is in range.
- It verifies that `NEW_NAME` is present.
- It then loops through all 7 days and calls `SetEntryName(newName)` on each matching entry that is allowed to be renamed.
- For each day, it sends the update to the protocol driver using the per-day `DAY_INDEX`, `ENTRY_INDEX`, and `ENTRY_NAME` values.

### Command sent to the protocol driver

- `UPDATE_SCHEDULE_ENTRY_NAME`
- Payload includes:
    - `DAY_INDEX`
    - `ENTRY_INDEX`
    - `ENTRY_NAME`

This is sent once per affected day, not as a single all-days command. 


### Returns

`None`

