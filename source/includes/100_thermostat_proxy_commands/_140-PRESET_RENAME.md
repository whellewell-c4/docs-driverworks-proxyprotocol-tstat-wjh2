## PRESET_RENAME

Renames an existing preset by its `PRESET_ID`. This command was added in 4.3.0.

### Name

`PRESET_RENAME ()`

### Parameters

| Parameter   | Type | Description                                                                             |
| ----------- | ---- | --------------------------------------------------------------------------------------- |
| `PRESET_ID` | INT  | Required. The identifier of the preset to rename.                                       |
| `NEW_NAME`  | STR  | Required. The new preset name. Must be a valid preset name and may not contain a comma. |

### Notes

- `PRESET_RENAME` is the 4.3.0 replacement for rename operations that previously relied on name-based matching.
- The preset is resolved by `PRESET_ID`; a name is not used for lookup.
- The new name must be valid and unique among existing presets.
- If the rename succeeds, the proxy updates the preset definition and updates any scheduled preset events that reference the renamed preset.

### Proxy behavior after completion

After a successful rename, the proxy updates the preset state, refreshes the preset list shown to the UI, and sends the updated preset data to the protocol driver as needed. Any preset event entries associated with that preset are also updated so the scheduler continues to reference the current preset name.

### Command Sent to Protocol Driver

`SET_PRESETS` - sends the updated preset XML payload to the protocol driver.

### Returns

`None`