# FLIGHT BOOKING DATABASE – QUERIES

## 01 Show all passengers

### Query
~~~sql
SELECT * FROM Passenger;
~~~

---

## 02 Flights from a specific city (Example: Delhi)

### Query
~~~sql
SELECT * FROM Flight
WHERE Source = 'Delhi';
~~~

---

## 03. Flights with price greater than 5000

### Query
~~~sql
SELECT * FROM Payment
WHERE Amount > 5000;
~~~

---

## 04. Count total passengers

### Query
~~~sql
SELECT COUNT(*) AS Total_Passengers FROM Passenger;
~~~

---

## 05. Average flight price

### Query
~~~sql
SELECT AVG(Amount) AS Average_Price FROM Payment;
~~~

---

## 06. Maximum flight price

### Query
~~~sql
SELECT MAX(Amount) AS Max_Price FROM Payment;
~~~

---

## 07. Booking details with passenger name (JOIN)

### Query
~~~sql
SELECT B.Booking_id, P.Name, B.Flight_id, B.Booking_date
FROM Booking B
JOIN Passenger P ON B.Passenger_id = P.Passenger_id;
~~~

---

## 08. Total bookings per flight

### Query
~~~sql
SELECT Flight_id, COUNT(*) AS Total_Bookings
FROM Booking
GROUP BY Flight_id;
~~~

---

## 09. Sort flights by price (descending)

### Query
~~~sql
SELECT * FROM Payment
ORDER BY Amount DESC;
~~~

---

## 20. Female passengers

### Query
~~~sql
SELECT * FROM Passenger
WHERE Gender = 'Female';
~~~

---

## 11. Payment details with booking

### Query
~~~sql
SELECT P.Payment_id, B.Booking_id, P.Amount, P.Payment_mode_id
FROM Payment P
JOIN Booking B ON P.Booking_id = B.Booking_id;
~~~

---

## 12. Flights between two cities (Example: Delhi to Mumbai)

### Query
~~~sql
SELECT * FROM Flight
WHERE Source = 'Delhi' AND Destination = 'Mumbai';
~~~

---

## 13. Passengers who have bookings

### Query
~~~sql
SELECT DISTINCT P.*
FROM Passenger P
JOIN Booking B ON P.Passenger_id = B.Passenger_id;
~~~

---

## 14. Total revenue

### Query
~~~sql
SELECT SUM(Amount) AS Total_Revenue FROM Payment;
~~~

---

## 15. Latest booking

### Query
~~~sql
SELECT * FROM Booking
ORDER BY Booking_date DESC
LIMIT 1;
~~~

---
