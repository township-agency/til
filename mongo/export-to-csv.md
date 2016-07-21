# Exporting Mongo data to CSV

You can use the `mongoexport` tool and pipe straight to a CSV file like so:

```
mongoexport -h localhost:27019 -d adjust -c events --csv --limit 1000 -f campaign,tracker,created_at,click_time,ip_address,engagement_time,country,region,gps_adid,adid,installed_at,event_name,userId,idfa -o export.csv
```
