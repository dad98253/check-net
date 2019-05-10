# check-net
daily cron job to check if raspberry pi zero-W has lost network connectivity

If it has lost connectivity, the machine is re-booted.

Put the script in /etc/cron.daily... make the owner is root:root and chmod to 755

note: you may need to install the ifupdown-extra package to get network-test!

The script will verbosely log the results of the network test to the system log file. This can be changed by adjusting the arguments to network-test.

The network-test application did not completely work out-of-the-box on my pi. The default web location used to find the external (web looking) ip address was blocked. If this is true for you as well, then use the CHECK_IP_URL environment variable to point to a location that works. Thus the "export CHECK_IP_URL=query-ip.com" in my script.


