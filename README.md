Bash Log Monitoring Script
--------------------------

Description:
-------------
This script monitors a specified log file in real-time for a given error pattern (e.g., "ERROR" or "CRITICAL"). 
It counts how many times the pattern appears within a specified time window and triggers an alert if it exceeds a defined threshold. 
The script also handles log rotation automatically using 'tail -F'.

Usage:
------
./log_monitor.sh <logfile> <pattern> <threshold> <time_window>

Arguments:
----------
<logfile>     : Path to the log file (e.g., /var/log/syslog)
<pattern>     : The error string or pattern to look for (e.g., "ERROR")
<threshold>   : Number of times the pattern must appear to trigger an alert (e.g., 10)
<time_window> : Time period in seconds over which occurrences are counted (e.g., 300 for 5 minutes)

Example:
--------
./log_monitor.sh /var/log/syslog "ERROR" 10 300

This will alert if "ERROR" appears 10 or more times within 5 minutes.

Steps to Execute:
-----------------

1. Make the script executable:
   chmod +x docker_monitoring.sh

3. Run the script with appropriate arguments. Example:
   ./docker_monitoring.sh /var/log/syslog "CRITICAL" 5 120

5. When the number of matches reaches the threshold within the time window, 
   the script will print an alert message like:
   [ALERT] 'CRITICAL' found 5 times in last 120 seconds!

