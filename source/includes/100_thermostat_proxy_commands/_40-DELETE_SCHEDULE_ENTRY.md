## DELETE\_SCHEDULE\_ENTRY

Deletes a schedule entry for one day or the full week, depending on whether DAY_INDEX is provided.

Introduced in OS Release 4.3.0.

### Name

`DELETE_SCHEDULE_ENTRY ()`


| Parameter   | Type | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ----------- | ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ENTRY_INDEX | INT  | `ENTRY_INDEX` is the zero-based index of the schedule entry for the selected day. In this implementation, the value is effectively offset by one relative to `schedule_entries_per_day`: if `schedule_entries_per_day` is 6, the valid entry indexes are 0 through 6, which represents 7 entries total. This is a legacy quirk of the schedule model, and the default value is 6 unless the default schedule overrides it through the `Entries` attribute on the `schedule_day_info` element in the `schedule_default` capability defined in the driver.xml file.                                    |
| DAY_INDEX   | INT  | `DAY_INDEX` is the zero-based index of the day in the weekly schedule. Valid values are 0 through 6, corresponding to the days of the week in the thermostat’s schedule model. This value is used with `ENTRY_INDEX` to identify the target schedule row: `DAY_INDEX` selects the day, and `ENTRY_INDEX` selects the entry within that day. If `DAY_INDEX` is provided, the command applies only to that day; if it is omitted, the command applies across all days for the selected entry index. The driver validates the value against the schedule’s weekly range and rejects invalid day values. |


### Command Sent to Protocol Driver

`DELETE_SCHEDULE_ENTRY`

## Notification

`SCHEDULE_ENTRY_DELETED`

Parameters:

- `EntryIndex`
- `DayIndex` (optional, included when the command applies to a specific day)

This notification is sent when a schedule entry is deleted. If the delete is scoped to a single day, both `EntryIndex` and `DayIndex` are included. If the delete applies across all days, the notification may include only `EntryIndex`.
### Returns

`None`
