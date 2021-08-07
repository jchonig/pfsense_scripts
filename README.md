# pfsense_scripts - Support scripts for pfSense routing software

[pfSense](https://www.pfsense.org/) support scripts

## Scripts

### gw_leds - Set LEDS on SG-3100 to indicate status of WAN links

This script sets the status of the LEDs on the SG-3100 to reflect the
status of monitored gateways.  The LEDs are a,b,c from left to right.

The colors are:

| Color  | Status                            | RGB Duty Cycles |
|--------|-----------------------------------|-----------------|
| Red    | Down or Forced Down               | 16 0 0          |
| Green  | Up with no issues (delay or loss) | 0 16 0          |
| Yellow | loss or delay                     | 0 16 4          |
| Orange | hight loss or delay               | 0 16 2          |
| Blue   | Unknown status                    | 0 0 16          |

+ Upload the file to root's home directory
+ Ensure it is executable
```sh
chmod 750 ./gw_leds
```
+ Ensure the cron package is installed
+ Add a cron job to run this job every minute.  Specify one or more
  parameters `-a`, `-b` and `-c` with the name of the gateway to
  monitor for a given LED.  For example:
```
/root/gw_leds -a WAN_OTTC_DHCP -b WAN_EA_DHCP
```

You can also use the `-A`, `-B` and `-C` options to provide a list of
red, green and blue duty cycles to fix an LED at a given color and
brightness.

For example, `-C 0,0,16` would light the right-most LED in a not-to
bright blue.

The duty cycles set from status are listed in the table obove.

