# ✈️ FLIGHT BOOKING DATABASE

## 01. Create Passenger Table

### Query
~~~sql
CREATE TABLE Passenger (
    Passenger_id INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT,
    Gender VARCHAR(10)
);
~~~

---

## 02. Create Flight Table

### Query
~~~sql
CREATE TABLE Flight (
    Flight_id INT PRIMARY KEY,
    Flight_name VARCHAR(50),
    Source VARCHAR(50),
    Destination VARCHAR(50)
);
~~~

---

## 03. Create Booking Table

### Query
~~~sql
CREATE TABLE Booking (
    Booking_id INT PRIMARY KEY,
    Passenger_id INT,
    Flight_id INT,
    Booking_date DATE,

    FOREIGN KEY (Passenger_id) REFERENCES Passenger(Passenger_id),
    FOREIGN KEY (Flight_id) REFERENCES Flight(Flight_id)
);
~~~

---

## 04. Create Payment Mode Table

### Query
~~~sql
CREATE TABLE Payment_Mode (
    Payment_mode_id INT PRIMARY KEY,
    Mode_name VARCHAR(30)
);
~~~

---

## 05. Create Payment Table

### Query
~~~sql
CREATE TABLE Payment (
    Payment_id INT PRIMARY KEY,
    Booking_id INT,
    Amount DECIMAL(10,2),
    Payment_mode_id INT,

    FOREIGN KEY (Booking_id) REFERENCES Booking(Booking_id),
    FOREIGN KEY (Payment_mode_id) REFERENCES Payment_Mode(Payment_mode_id)
);
~~~

---
