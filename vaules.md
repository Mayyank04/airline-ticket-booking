# ✈️ FLIGHT BOOKING DATABASE – SAMPLE DATA

## 06. Insert into Passenger Table

### Query
~~~sql
INSERT INTO Passenger VALUES
(1, 'Aman', 21, 'Male'),
(2, 'Riya', 22, 'Female'),
(3, 'Rahul', 25, 'Male'),
(4, 'Sneha', 23, 'Female'),
(5, 'Arjun', 28, 'Male'),
(6, 'Pooja', 24, 'Female'),
(7, 'Karan', 27, 'Male'),
(8, 'Neha', 26, 'Female'),
(9, 'Vikas', 30, 'Male'),
(10, 'Anjali', 22, 'Female'),
(11, 'Rohit', 29, 'Male'),
(12, 'Meena', 31, 'Female');
~~~

---

## 07. Insert into Flight Table

### Query
~~~sql
INSERT INTO Flight VALUES
(101, 'Indigo101', 'Delhi', 'Mumbai'),
(102, 'AirIndia202', 'Delhi', 'Bangalore'),
(103, 'SpiceJet303', 'Mumbai', 'Chennai'),
(104, 'Vistara404', 'Delhi', 'Kolkata'),
(105, 'Indigo505', 'Chennai', 'Delhi'),
(106, 'AirIndia606', 'Bangalore', 'Mumbai'),
(107, 'SpiceJet707', 'Kolkata', 'Delhi'),
(108, 'Vistara808', 'Mumbai', 'Goa'),
(109, 'Indigo909', 'Goa', 'Delhi'),
(110, 'AirIndia111', 'Delhi', 'Hyderabad');
~~~

---

## 08. Insert into Booking Table

### Query
~~~sql
INSERT INTO Booking VALUES
(1001, 1, 101, '2026-04-01'),
(1002, 2, 102, '2026-04-02'),
(1003, 3, 103, '2026-04-03'),
(1004, 4, 104, '2026-04-04'),
(1005, 5, 105, '2026-04-05'),
(1006, 6, 106, '2026-04-06'),
(1007, 7, 107, '2026-04-07'),
(1008, 8, 108, '2026-04-08'),
(1009, 9, 109, '2026-04-09'),
(1010, 10, 110, '2026-04-10'),
(1011, 11, 101, '2026-04-11'),
(1012, 12, 102, '2026-04-12');
~~~

---

## 09. Insert into Payment Mode Table

### Query
~~~sql
INSERT INTO Payment_Mode VALUES
(1, 'UPI'),
(2, 'Card'),
(3, 'Net Banking'),
(4, 'Cash');
~~~

---

## 10. Insert into Payment Table

### Query
~~~sql
INSERT INTO Payment VALUES
(5001, 1001, 4500.00, 1),
(5002, 1002, 6500.00, 2),
(5003, 1003, 5000.00, 3),
(5004, 1004, 4800.00, 1),
(5005, 1005, 7000.00, 2),
(5006, 1006, 5500.00, 4),
(5007, 1007, 6200.00, 3),
(5008, 1008, 4300.00, 1),
(5009, 1009, 3900.00, 2),
(5010, 1010, 7200.00, 3),
(5011, 1011, 4600.00, 1),
(5012, 1012, 6800.00, 2);
~~~

---
