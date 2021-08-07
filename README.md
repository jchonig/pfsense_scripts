# pfsense_scripts - Support scripts for pfSense routing software

[pfSense](https://www.pfsense.org/) support scripts

## Scripts

### gw_leds - Set LEDS on SG-3100 to indicate status of WAN links

+ Edit the case statement at the end of the file to match your gateway names
+ Upload the file to root's home directory
+ Ensure it is executable
```sh
chmod 750 ./gw_leds
```
+ Ensure the cron package is installed
+ Add a cron job to run this job every minute
