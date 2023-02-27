Catalyst 9800 WLC Calendar Template scheduling

To enable power save mode on Cisco Catalyst Access Points

```
wireless profile power "Off Work Hours"
 0 radio 6ghz state shutdown
 1 radio secondary-5ghz state shutdown
 2 usb 0 state disable
 3 radio 5ghz state shutdown

wireless profile calender-profile name "Off Work 5PM to Midnight"
 day monday
 day tuesday
 day wednesday
 day thursday
 day friday
 recurrance weekly
 start 17:00:00 end 23:59:59

wireless profile calender-profile name "Off Work Midnight to 8AM"
 day monday
 day tuesday
 day wednesday
 day thursday
 day friday
 recurrance weekly
 start 00:00:00 end 08:00:00

ap profile default-ap-profile
 calendar-profile "Workday 5pm to Midnight"
  action power-saving-mode power-profile "Off Work Hours"
 calendar-profile "Workday Midnight to 8am"
  action power-saving-mode power-profile "Off Work Hours"
```
