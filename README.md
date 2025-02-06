# SQL-Indore-Ola-Ride-Analysis
## BASIC LEVEL QUESTIONS

### 1. Retrieve all records from the booking table.
```sql
SELECT * FROM booking;
```

### 2. Find the total number of bookings in the booking table.
```sql
select count(*) as Total_Booking from booking;
```

### 3. Retrieve all bookings where Booking_Status is "Completed".
```sql
select * from booking
where booking_status = 'success';
```

### 4. Retrieve the first 10 records from the booking table.
```sql
select top 10 * from booking;
```

### 5. Find the customers (Customer_ID) who have booked more than 3 rides.
```sql
select customer_id,count(*) as Number_of_booking from booking
group by customer_id
having count(*) >3;
```

### 6. Get the total number of cancelled rides by customers
```sql
select count(*) as number_of_cancel_rides from booking
where Canceled_Rides_by_Customer = 1;
```

### 7. Retrieve the total booking amount for rides that were successfully completed.
```sql
select sum(booking_value) as Total_booking_amount
from booking
where booking_status = 'success';
```

### 8. Retrieve the number of Booking where driver rating above 4.5
```sql
select count(*) as Number_of_booking from booking
where driver_ratings > 4.5;
```

### 9. Find the average ride distance for each vehicle type
```sql
select vehicle_type, avg(ride_distance) as avg_distance from booking
group by vehicle_type
order by avg(ride_distance) desc;
```

### 10. Get the number of rides cancelled by drivers due to personal and car-related issues
```sql
select count(*) as Cancelled_rides from booking
where Reason_for_canceling_by_Driver = 'Personal & Car related issue';
```

## INTERMEDIATE LEVEL QUESTIONS

### 11. Find the number of rides per vehicle type.
```sql
SELECT vehicle_type,count(*) as Number_of_rides
from booking
group by vehicle_type
order by count(*) desc;
```

### 12. Calculate the average ride fare for all successful rides.
```sql
select avg(booking_value) as average_fare from booking
where booking_status = 'success';
```

### 13. Get the highest ride distance for each vehicle type.
```sql
select vehicle_type, max(ride_distance) AS max_distance
from booking
group by vehicle_type;
```

### 14. List the top 5 customers who have spent the most on bookings.
```sql
select top 5 customer_id,sum(booking_value) as Total_spending
from booking
group by customer_id
order by sum(booking_value);
```

### 15. Find all customers who have made bookings in multiple locations.
```sql
select customer_id from booking
group by customer_id
having count(distinct drop_location) > 1;
```

### 16. Find the most popular vehicle type based on the number of bookings.
```sql
select top 1 vehicle_type,count(*) as Number_of_booking from booking
group by vehicle_type
order by count(*) desc;
```

## ADVANCED LEVEL QUESTIONS

### 17. Find the total ride distance for each vehicle type and display it in descending order.
```sql
select vehicle_type,round(sum(ride_distance),2) as total_ride_distance from booking
group by vehicle_type
order by sum(ride_distance);
```

### 18. Calculate the percentage of rides that were canceled by drivers.
```sql
select
(count(case when canceled_rides_by_driver = 1 then 1 end) * 100.0 / count(*))  as driver_cancellation_percentage
from booking
where booking_status != 'success';
```

### 19. Retrieve the most frequent cancellation reasons provided by customers.
```sql
select reason_for_canceling_by_customer,count(*) as frequency
from booking
group by reason_for_canceling_by_customer
order by count(*) desc;
```
## 📞 Contact

If you have any questions or want to connect, feel free to reach out:

- 📧 Email: [vinaypanika@gmail.com](mailto:vinaypanika@gmail.com)
- 💼 LinkedIn: [Vinay Kumar Panika](https://www.linkedin.com/in/vinaykumarpanika)
- 📂 GitHub: [VinayPanika](https://github.com/Vinaypanika)
- 🌐 Portfolio: [Visit My Portfolio](https://sites.google.com/view/vinaykumarpanika/home)
- 📞 Mobile: [+91 7415552944](tel:+917415552944)
