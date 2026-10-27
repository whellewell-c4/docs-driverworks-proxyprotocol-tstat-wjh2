
## RESTORE_SCHEDULE_ENTRY

Restores a previously deleted schedule entry. This command was added in 4.3.0.

### Name

`RESTORE_SCHEDULE_ENTRY ()`

### Parameters

| Parameter     | Type | Description                                                                                                                      |
| ------------- | ---- | -------------------------------------------------------------------------------------------------------------------------------- |
| `ENTRY_INDEX` | INT  | Required. The schedule entry index to restore.                                                                                   |
| `DAY_INDEX`   | INT  | Optional. If supplied, only the specified day is restored. If omitted, the restore applies across all days for that entry index. |
|               |      |                                                                                                                                  |

### Notes

- `ENTRY_INDEX` is zero-based and refers to the schedule entry within the selected day.
- `DAY_INDEX` is zero-based and valid from 0 to 6. 0 = Sunday.
- If `DAY_INDEX` is omitted, the command attempts to restore the deleted entry on all days at that entry index.
- The command only restores entries that are currently marked as deleted.
- If no matching deleted entry is found, the restore request is ignored.


### Command Sent to Protocol Driver

`RESTORE_SCHEDULE_ENTRY` - sends the restore operation to the protocol driver with the relevant `DAY_INDEX` and `ENTRY_INDEX` values.

### Returns

`None`