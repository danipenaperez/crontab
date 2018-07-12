# crontab
Example of simple file configuration crontab

Attached to this repo exists a simple crontab file
In CentOS the cron configuration file lives in /etc/crontab 

```
> sudo vi /etc/crontab
```

This a simple example:
```
SHELL=/bin/bash
PATH=/sbin:/bin:/usr/sbin:/usr/bin
MAILTO=root
HOME=/

# For details see man 4 crontabs

# Example of job definition:
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  * user-name command to be executed
* * * * * root /bin/echo "running" > /home/daniel.pena/file.txt
```

In this example will echo "running" to file.txt every minute 

If you edit the file, you must reload the crontab service to refresh
```
>sudo service crond reload
```

Another cron scheduled configuration could be:
```
@yearly        Run once a year, "0 0 1 1 *".
@monthly       Run once a month, "0 0 1 * *".
@weekly        Run once a week, "0 0 * * 0".
@daily         Run once a day, "0 0 * * *".
@midnight      (same as @daily)
@hourly        Run once an hour, "0 * * * *".
All days at 23 hours (and 0 minutes):
0 23 * * *
All days at 23 hours (and every minute between 23:00 and 23:59):
* 23 * * *
```

Some info extracted from https://www.pantz.org/software/cron/croninfo.html

