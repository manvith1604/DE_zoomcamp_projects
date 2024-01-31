## Question 3. Count records

## Question 4. Longest trip for each day



## Question 5. Three biggest pickups

```sql
SELECT zp.Borough, SUM(t.total_amount) FROM green_tripdata t , zone zp, zone zd
where t.PULocationID = zp.LocationID AND 
t.DOLocationID = zd.LocationID AND
t.total_amount > 50000
group by zp.Borough
order by SUM(t.total_amount) desc
```
Queens  700574.9699997478</br>
Brooklyn  587201.7999998855</br>
Manhattan  569632.6499997162</br>



