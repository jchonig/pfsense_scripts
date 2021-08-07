# pfsense_scripts - Support scripts for pfSense routing software

[pfSense](https://www.pfsense.org/) support scripts

## Scripts

### gw_leds - Set LEDS on SG-3100 to indicate status of WAN links

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
