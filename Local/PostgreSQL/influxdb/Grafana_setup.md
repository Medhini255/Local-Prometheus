#  How to View Graph in Grafana

1. Go to **Grafana Dashboard** → Add Panel → Time Series.
2. Select your **data source** as `influxdb-2` or your custom one.
3. Run a query like:
```sql
SELECT mean("total_rows") FROM "test_table_rows" WHERE $timeFilter GROUP BY time($__interval) fill(null)
```
4. Adjust time range (top-right) to `Last 6 hours` or `Last 30 mins`.
5. Save dashboard.

You should now see your test_table count changing as you insert new rows!
