source: Support/Cleanup-options.md

#  Cleanup Options
As the number of devices starts to grow in your LibreNMS install, so will things such as the RRD files, MySQL database containing eventlogs, Syslogs and performance data etc. Your LibreNMS install could become quite large so it becomes necessary to clean up those entries. With Cleanup Options, you can keep in crontrol. 

These options rely on ```daily.sh``` running from cron as per the installation instructions.

Cleanup Options are set in ```config.php```

```php
$config['syslog_purge']                                   = 30;
$config['eventlog_purge']                                 = 30;
$config['authlog_purge']                                  = 30;
$config['perf_times_purge']                               = 30;
$config['device_perf_purge']                              = 7;
$config['rrd_purge']                                      = 90;// Not set by default
```
These options will ensure data within LibreNMS over X days old is automatically purged. You can alter these individually, values are in days.

**NOTE**: Please be aware that ```$config['rrd_purge']``` is NOT set by default. This option will remove any old data within the rrd directory automatically - only enable this if you are comfortable with that happening.