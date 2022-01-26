### Question 3

```sql
SELECT
  COUNT(trip_distance)
FROM
  `aeros-sandbox-juani.projects.yellow_taxi_trips`
WHERE
  CAST(tpep_pickup_datetime AS date) = '2021-01-15'
```

### Question 4

```sql
SELECT
  tip_amount,
  tpep_pickup_datetime
FROM
  `aeros-sandbox-juani.projects.yellow_taxi_trips`
ORDER BY
  tip_amount DESC
LIMIT
  1
```

### Question 5

```sql
SELECT
  COUNT(*) AS dest_count,
  zone.LocationID,
  zone.Borough,
  zone.Zone AS Zona
FROM
  `aeros-sandbox-juani.projects.yellow_taxi_trips` AS trips
LEFT JOIN
  `aeros-sandbox-juani.projects.yellow_taxi_zone` AS zone
ON
  trips.DOLocationID = zone.LocationID
WHERE
  CAST(tpep_pickup_datetime AS date) = '2021-01-14'
GROUP BY
  zone.LocationID,
  zone.Borough,
  zone.Zone
ORDER BY
  dest_count DESC
LIMIT
  1
```

### Question 6