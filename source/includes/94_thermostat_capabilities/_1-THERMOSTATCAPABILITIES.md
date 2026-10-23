## THERMOSTAT CAPABILITIES

The following Capabilities are supported with the Thermostat Proxy. 

Note the reference to the [Dynamic Capabilities Changed][1] notification in many of the capabilities defined below. Using the Dynamic Capabilities notify  is a way for a protocol driver to send updates about some capabilities that can be changed when settings change on the hardware.  An example would be a thermostat that now includes a humidifier. The thermostat would need to tell the proxy it can now do humidification. The  `<can_humidify></can_humidify>`  capability is designated as  a capability that can be changed using Dynamic Capabilities Changed. The capability can be passed as a parameter in the notify to update the thermostat proxy regarding humidification ability.

Additionally, please see the Samples folder delivered in this SDK for additional Thermostat (V2) code examples.

#### `<can_calibrate></can_calibrate>`
Indicates if the device is capable of calibrating itself. Enables the `SET_CALIBRATION` command. Valid values: True/False.



#### `<can_change_scale></can_change_scale>`
Boolean to enable/disable Navigator UIs and ComposerPro from being able to change the scale of the hardware. Valid values: True/False. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][2] notification.



#### `<can_cool></can_cool>`
Indicates if this thermostat supports cooling and indicates to UIs and Programming that the device could execute this functionality. Valid values: True/False. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][3] notification.


#### `<can_dehumidify></can_dehumidify>`
Boolean to enable/disable `can_dehumidity` capability, if the device supports this feature, default is True. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][4] notification. This is older functionality that indicated to UI's and Programming that the device could execute this functionality.  However, their limitation is that they do not take into account if the current HVAC mode supported them.  HVAC Modes replaced their functionality, but older drivers still use them and they do work. Control4  recommends the use of HVAC Modes now and that this capability be set to false in the driver's configuration file.


#### `<can_do_auto></can_do_auto>`
 Indicates if this thermostat can automatically switch from heat to cool and indicates to UIs and Programming that the device could execute this functionality. If the device can deadband enforcement, it will be done on the UIs as specified with the deadband capabilities. Valid values: True/False. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][5] notification.


#### `<can_fixed_schedule_and_presets></can_fixed_schedule_and_presets>`
Introduced in 4.3.0. Indicates support for both the legacy schedule plus presets. When `<can_fixed_schedule_and_presets>` is true then `<can_preset>` and `<can_preset_schedule>` should be set to false. This capability allows the driver to use the legacy scheduler along with supporting presets. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][6] notification.


#### `<can_heat></can_heat>`
Indicates if this thermostat supports heating  and indicates to UIs and Programming that the device could execute this functionality. Valid values: True/False. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][6] notification.


#### `<can_humidify></can_humidify>`
Boolean to enable/disable `can_humidity` capability, if the device supports this feature, default is True. It indicates to UIs and Programming that the device could execute this functionality. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][7] notification. 


#### `<can_inc_dec_setpoints></can_inc_dec_setpoints>`
Boolean indicating if the device has internal commands to increment and decrement both heat and cool set points independently. If false the proxy will take the current setpoint and +/- 1 (or the resolution) and send a [`DYNAMIC_CAPABILITIES_CHANGED` ][8] command with the new setpoint value, which could potentially send 81 three times if someone did programming of Increment Setpoint and the current setpoint was 80, rather than sending 83 as someone might expect from Composer Programming of 3 increment commands without a sleep between that provides enough time for the hardware to set each increment and return the new setpoint to director before the next Increment occurs.


#### `<can_lock_buttons></can_lock_buttons>`
 Indicates if the buttons on the TSTAT can be locked out to prevent changes. Valid values: True/False.


#### `<can_lock_screen></can_lock_screen>`
Introduced in 4.3.0. Indicates if the screen on the thermostat device is able to be locked. The modes that are supported are provided by the `<lock_screen_modes>` capability. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][6] notification.


#### `<lock_screen_modes></lock_screen_modes>`
Introduced in 4.3.0. Comma delimited string of possible screen-lock modes. Used with '<can_lock_screen'.  For example: Unlocked,Partially Locked,Fully Locked. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][6] notification.


#### `<can_preset></can_preset>`
Boolean indicating if the device supports the preset functionality including `custom_fields`. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][9] notification.


#### `<can_preset_schedule></can_preset_schedule>`
Boolean indicating if the thermostat will support the `SET_EVENTS` commands for running presets based on scheduling created in Navigators. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][10] notification.


#### `<current_temperature_max_c></current_temperature_max_c>`
Double indicating the maximum temperature that the thermostat will report in C. Default is 48. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][11] notification.


#### `<current_temperature_min_c></current_temperature_min_c>`
Double indicating the minimum temperature that the thermostat will report in C. Default is -40. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][12] notification.


#### `<current_temperature_max_f></current_temperature_max_f>`
Double indicating the maximum temperature that the thermostat will report in F. Default is 120. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][13] notification.


#### `<current_temperature_min_f></current_temperature_min_f>`
Double indicating the minimum temperature that the thermostat will report in F. Default is -40. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][14] notification.


#### `<current_temperature_resolution_c></current_temperature_resolution_c>`
Double indicating the increments that the temperature will follow, such as .1, .5, 1, 2, 5, etc. Default is 1. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][15]notification.


#### `<current_temperature_resolution_f></current_temperature_resolution_f>`
Double indicating the increments that the temperature will follow, such as .2, .5, 1, 2, 5, etc. Default is 1. Note .2 is the lowest F resolution supported. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][16] notification.


#### `<fan_modes></fan_modes>`
This is a comma delimited list of possible fan modes this thermostat supports. For example: Auto, Low, Medium, High with no spaces after the comma. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][17] notification.


#### `<fan_states></fan_states>`
This is a comma delimited list of all the possible states that the HVAC system fan supports. For example: Off, On, Low, Med, Circulate with no spaces after the commas. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][18] notification.


#### `<has_humidity></has_humidity>`
Boolean indicating if the device can report the current humidity. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][19] notification.


#### `<has_extras></has_extras>`
Boolean indicating if the device has extras commands support. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][20] notification.


#### `<has_connection_status></has_connection_status>`
Boolean indicating if the device reports online/offline status of the hardware device, this is often forgotten about but very important to implement in new protocol drivers drivers.


#### `<has_outdoor_temperature></has_outdoor_temperature>`
Boolean indicating if the device can provide an outdoor temperature. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][21] notification.


#### `<has_remote_sensor></has_remote_sensor>`
Indicates if this thermostat has a remote sensor. Valid values: True/False.


#### `<has_single_setpoint></has_single_setpoint>`
 Boolean indicating if the device is single setpoint.  `can_heat, can_cool` and `can_auto` should be set to false if this option is used. It indicates to UIs and Programming that the device could execute this functionality.  This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][22] notification. 


#### `<has_temperature></has_temperature>`
Boolean indicating if the device can provide a temperature of the thermostat/room. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][23] notification.


#### `<has_vacation_mode></has_vacation_mode>`
Indicates if this thermostat supports vacation mode Valid values: True/False
The capability `has_vacation_mode` must be set to true for the vacation commands and notifications to be executed. Preset Scheduling and Vacation Mode are mutually exclusive and drivers should really use Preset Scheduling to accomplish what Vacation Mode has done in the past.


#### `<hold_modes></hold_modes>`
This is a comma delimited list of the possible hold modes this thermostat supports. Valid values include: Off, 2 Hours, Until Next, Permanent with no spaces after the commas. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][24] notification.


#### `<hold_until_mode></hold_until_mode>`
Introduced in 4.3.0. Controls whether Hold Until uses `time` semantics or `date,time` semantics. The default is `date,time`. Some thermostats only supports setting the hold until mode within a 24 hour period and only supplies the time. If this is the case then set `<hold_until_mode>` to "time".


#### `<hold_until_resolution></hold_until_resolution>`
Introduced in 4.3.0. Minute resolution used for Hold Until rounding and UI input behavior. Double indicating the increments that the hold_until  will follow, such as 1, .5, 10 etc. Default is 5.


#### `<humidity_modes></humidity_modes>`
A comma separated list of all the modes the device supports. For example: "Off,Humidify,Dehumidify,Auto" with no spaces after the commas. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][25] notification.


#### `<humidity_states></humidity_states>`
 A comma separated list of all the modes the device supports. Usually something like "Off,Humidifying,Dehumidifying", with no spaces after the commas.


#### `<hvac_modes></hvac_modes>`
A comma separated list of all the modes the device supports. For example:  "Off,Heat,Cool", with no spaces after the commas.


#### `<hvac_states></hvac_states>`
This is a comma delimited list that represents all of the possible states that the HVAC system supports. For example: Off, Heat, Cool, Heating, Stage 1 Cool, etc with no spaces after the commas


#### `<outdoor_temperature_resolution_c></outdoor_temperature_resolution_c>`
Double indicating the increments that the temperature will follow, such as .2, .5, 1, 2, 5, etc. Default is 1. Note that .2 is the lowest C resolution supported. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][26] notification.


#### `<outdoor_temperature_resolution_f></outdoor_temperature_resolution_f>`
Double indicating the increments that the temperature will follow, such as .2, .5, 1, 2, 5, etc. Default is 1. Note .2 is the lowest F resolution supported. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][27] notification.


#### `<preset_fields></preset_fields>`
XML of fields for settings that are potentially unique to the protocol driver, yet will be displayed in the UI during the creation or modification of presets for scheduling. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][28] notification.


#### `<scheduling></scheduling>`
A boolean indicating if the device supports a programmed schedule. If it is true, it should have a `schedule_default` entry in the capabilities section in the driver.xml file. Mutually exclusive to Preset Scheduling unless `can_fixed_schedule_and_presets` is true. In 4.3.0, `scheduling` and `schedule_default` can be handled dynamically. If either capability is missing from the static capability set, thermostatV2 proxy treats it through the dynamic capability flow. If `scheduling` is true and the driver is not providing `schedule_default` through that dynamic flow, the driver should provide a `schedule_default` block in `driver.xml`.


#### `<schedule_default></schedule_default>`
An XML block indicating the default schedule for the device.  Legacy scheduling is mutually exclusive to preset scheduling unless `can_fixed_schedule_and_presets` is true which was introduced in 4.3.0. In 4.3.0, `scheduling` and `schedule_default` can be handled dynamically. If either capability is missing from the static capability set, thermostatV2 proxy treats it through the dynamic capability flow. If `scheduling` is true and the driver is not providing `schedule_default` through that dynamic flow, the driver should provide a `schedule_default` block in `driver.xml`. See the example below.


```xml
<schedule_default>
    <schedule_day_info Entries = "6" DefaultHeat = "200" DefaultCool = "278">
        <schedule_entry Name = "Wake" Time = "360" Enabled = "True" CanChangeName="False" CanDelete="False"/>
        <schedule_entry Name = "Leave" Time = "480" Enabled = "True" CanChangeName="False" CanDelete="False"/>
        <schedule_entry Name = "Return" Time = "1080" Enabled = "True" CanChangeName="False" CanDelete="False"/>
        <schedule_entry Name = "Sleep" Time = "1320" Enabled = "True" CanChangeName="False" CanDelete="False"/>
        <schedule_entry Name = "Custom 1" Time = "1380" Enabled = "False" CanChangeName="True" CanDelete="True"/>
        <schedule_entry Name = "Custom 2" Time = "1380" Enabled = "False" CanChangeName="True" CanDelete="True"/>
    </schedule_day_info>
</schedule_default>

```
#### `<schedule_entry></schedule_entry>`
There is one `<schedule_entry>` for each schedule entry during the day. Each entry attribute defines that entry. The following table describes each of the potential attributes. CanChangeName and CanDelete were added in OS Release 4.3.0.

| Attribute     | Version | Value      | Description                                                                                                                                   |
| ------------- | ------- | ---------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Name          |         | String     | Indicates the name of the entry that will show up in composer and navigator.                                                                  |
| Time          |         | Number     | Indicates the name of the entry that will show up in composer and navigator. The time units are minutes since midnight, so 360 means 6:00 AM. |
| Enabled       |         | True/False | Indicates whether or not this entry is initially enabled or not.                                                                              |
| CanChangeName | 4.3.0   | True/False | Indicates whether or not this entry name can be changed. This is optional. Default is False.                                                  |
| CanDelete     | 4.3.0   | True/False | Indicates whether or not this entry can be deleted. This is optional. Default is False.                                                       |
In the example used here, there are six schedule entries.

```xml
<schedule_day_info>
   <schedule_entry Name="Awake" Time="360" Enabled="True" CanChangeName="False" CanDelete="False" />
   <schedule_entry Name="Leave" Time="480" Enabled="True" CanChangeName="False" CanDelete="False" />
   <schedule_entry Name="Return" Time="1080" Enabled="True" CanChangeName="False" CanDelete="False" />
   <schedule_entry Name="Sleep" Time="1320" Enabled="True" CanChangeName="False" CanDelete="False" />
   <schedule_entry Name="Custom 1" Time="1380" Enabled="False" CanChangeName="True" CanDelete="True" />
   <schedule_entry Name="Custom 2" Time="1380" Enabled="False" CanChangeName="True" CanDelete="True" />
</schedule_day_info>
```

#### `<setpoint_cool_max></setpoint_cool_max>`
Integer indicating the highest temperature the cool setpoint can be configured as. Default is 89. If used,`_f `and `_c` do not need to be set but since this value is Celsius x 10, it will result in a potentially undesired Fahrenheit conversion.  This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][29] notification.


#### `<setpoint_cool_max_c></setpoint_cool_max_c>`
Integer indicating the highest temperature the cool setpoint can be configured as. Default is 90. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][30] notification.



#### `<setpoint_cool_max_f></setpoint_cool_max_f>`
Integer indicating the highest temperature the cool setpoint can be configured as. Default is 89. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][31] notification.


#### `<setpoint_cool_min></setpoint_cool_min>`
Integer indicating the lowest temperature the cool setpoint can be configured as. Default is 39. If used,`_f` and `_c` do not need to be set but since this value is Celsius x 10 it will result in a potentially undesired Fahrenheit conversion. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][32] notification.


#### `<setpoint_cool_min_c></setpoint_cool_min_c>`
 Integer indicating the lowest temperature the cool setpoint can be configured as. Default is 42. If used, `_f` and `_c` do not need to be set but since this value is Celsius x 10 it will result in a potentially undesired Fahrenheit conversion. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][33] notification.


#### `<setpoint_cool_min_f></setpoint_cool_min_f>`
Integer indicating the lowest temperature the cool setpoint can be configured as. Default is 42. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][34]  notification.


#### `<setpoint_cool_resolution_c></setpoint_cool_resolution_c>`
Double indicating the increments that the setpoint will follow, such as .1, .5, 1, 2, 5, etc. Default is 1. This capability can be changed through a C notification.


#### `<setpoint_cool_resolution_f></setpoint_cool_resolution_f>`
Double indicating the increments that the setpoint will follow, such as .1, .5, 1, 2, 5, etc. Default is 1. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][35] notification.


#### `<setpoint_heatcool_deadband_c></setpoint_heatcool_deadband_c>`
Double indicating the deadband range in Celcius that the hardware requires between heat and cool.  Default is 2.  Default is 2.  Post operating system 2.7.0, UI's will show both heat and cool setpoints moving if in Auto and the movement will be based on this deadband value. If a user tries to move heat above cool or cool below heat, the UI's will only send the setpoint command for the primarily moving setpoint.  A protocol driver will need to send two notifies back, one for heat and one for cool if in fact both setpoints were changed on the hardware. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][36] notification.


#### `<setpoint_heatcool_deadband_f></setpoint_heatcool_deadband_f>`
Double indicating the deadband range in Fahrenheit  that the hardware requires between heat and cool.  Default is 2.  Post operating system 2.7.0, UI's will show both heat and cool setpoints moving if in Auto and the movement will be based on this deadband value. If a user tries to move heat above cool or cool below heat, the UI's will only send the setpoint command for the primarily moving setpoint.  A protocol driver will need to send two notifies back, one for heat and one for cool if in fact both setpoints were changed on the hardware. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][37] notification.


#### `<setpoint_heat_max></setpoint_heat_max>`
Integer indicating the highest temperature the heat setpoint can be configured as. Default is 88. If used, `_f `and`_c` do not need to be set but since this value is Celsius x 10 it will result in a potentially undesired Fahrenheit conversion. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][38] notification.


#### `<setpoint_heat_max_c></setpoint_heat_max_c>`
Integer indicating the highest temperature the heat setpoint can be configured as. Default is 31. Best to use `_f `and `_c` and not the older celsius x 10 capability.  This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][39] notification.


#### `<setpoint_heat_max_f></setpoint_heat_max_f>`
Integer indicating the highest temperature the heat setpoint can be configured as. Default is 89. Best to use `_f `and `_c` and not the older celsius x 10 capability.  This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][40] notification.


#### `<setpoint_heat_min></setpoint_heat_min>`
Integer indicating the lowest temperature the heat setpoint can be configured as. Default is 40. If used, `_f` and `_c `do not need to be set but since this value is Celsius x 10 it will result in a potentially undesired Fahrenheit conversion. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][41] notification.


#### `<setpoint_heat_min_c></setpoint_heat_min_c>`
Integer indicating the lowest temperature the heat setpoint can be configured as. Default is 4. Best to use `_f` and `_c` and not the older Celsius x 10 capability. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][42] notification.


#### `<setpoint_heat_min_f></setpoint_heat_min_f>`
Integer indicating the lowest temperature the heat setpoint can be configured as. Default is 38. Best to use `_f` and `_c` and not the older celsius x 10 capability. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][43] notification.


#### `<setpoint_heat_resolution_c></setpoint_heat_resolution_c>`
Double indicating the increments that the setpoint will follow, such as .1, .5, 1, 2, 5, etc. Default is 1. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][44] notification.


#### `<setpoint_heat_resolution_f></setpoint_heat_resolution_f>`
Double indicating the increments that the setpoint will follow, such as .1, .5, 1, 2, 5, etc. Default is 1. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][45] notification.


#### `<setpoint_dehumidify_max></setpoint_dehumidify_max>`
Integer indicating the highest dehumidify setpoint, default 100.  This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][46] notification.


#### `<setpoint_dehumidify_min></setpoint_dehumidify_min>`
Integer indicating the lowest dehumidify setpoint, default 0.  This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][47] notification.


#### `<setpoint_humidify_min></setpoint_humidify_min>`
Integer indicating the lowest humidify setpoint, default 0. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][48] notification.


#### `<setpoint_humidify_max></setpoint_humidify_max>`
Integer indicating the highest humidify setpoint, default 100. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][49] notification.


#### `<setpoint_humidify_resolution></setpoint_humidify_resolution>`
Integer indicating the increments that the setpoint will follow, Default is 1. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][50] notification.


#### `<setpoint_dehumidify_resolution></setpoint_dehumidify_resolution>`
 Integer indicating the increments that the setpoint will follow, Default is 1. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][51] notification.


#### `<setpoint_single_max_c></setpoint_single_max_c>`
Integer indicating the highest temperature the single setpoint can be configured as. Default is 32. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][52] notification.


#### `<setpoint_single_max_f></setpoint_single_max_f>`
Integer indicating the highest temperature the single setpoint can be configured as. Default is 90. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][53] notification.


#### `<setpoint_single_min_c></setpoint_single_min_c>`
Integer indicating the lowest temperature the single setpoint can be configured as. Default is 4. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][54] notification.


#### `<setpoint_single_min_f></setpoint_single_min_f>`
Integer indicating the lowest temperature the single setpoint can be configured as. Default is 38. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][55] notification.


#### `<setpoint_heat_resolution_f></setpoint_heat_resolution_f>`
Double indicating the increments that the setpoint will follow, such as .2, .5, 1, 2, 5, etc. Default is 1. Note .2 is the lowest F resolution supported. This capability can be changed through a [`DYNAMIC_CAPABILITIES_CHANGED` ][56] notification.



[1]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[2]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[3]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[4]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[5]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[6]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[7]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[8]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[9]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstatt
[10]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstatt
[11]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[12]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[13]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[14]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[15]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[16]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[17]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[18]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[19]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[20]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[21]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[22]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[23]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[24]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstatt
[25]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[26]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[27]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[28]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[29]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[30]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[31]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[32]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[33]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[34]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[35]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[36]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[37]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[38]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[39]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[40]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[41]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[42]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[43]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[44]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[45]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[46]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[47]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[48]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#dynamic-capabilities-changed-tstat
[49]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[50]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[51]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[52]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[53]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[54]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[55]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat
[56]:	https://snap-one.github.io/docs-driverworks-proxyprotocol/#thermostat-notifications-dynamic_capabilities_changed-tstat