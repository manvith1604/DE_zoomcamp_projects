## Question 3. Count records
```sql
SELECT count(1) from green_tripdata
WHERE (date(lpep_pickup_datetime) = '2019-09-18') AND (date(lpep_dropoff_datetime) = '2019-09-18')
```
Ans : 15612

## Question 4. Longest trip for each day
```sql
SELECT
    lpep_pickup_datetime,
    DATEDIFF(minute, lpep_dropoff_datetime, lpep_pickup_datetime) AS duration
FROM
    green_tripdata
ORDER BY
    duration desc;
```
Ans : 2019-09-26 08:58:52 6045.033332929015

## Question 5. Three biggest pickups

```sql
SELECT zp.Borough, SUM(t.total_amount) FROM green_tripdata t , zone zp, zone zd
where t.PULocationID = zp.LocationID AND 
t.DOLocationID = zd.LocationID AND
t.total_amount > 50000
group by zp.Borough
order by SUM(t.total_amount) desc
```
Ans : Queens  700574.9699997478</br>
Brooklyn  587201.7999998855</br>
Manhattan  569632.6499997162</br>

## Question 6. Largest tip

```sql
SELECT * FROM green_tripdata t , zone zp, zone zd
where t.PULocationID = zp.LocationID AND 
t.DOLocationID = zd.LocationID
AND zp.Zone = 'Astoria'
order by t.tip_amount desc
```
Ans : JFK airport


