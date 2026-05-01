 Passenger Table
CREATE TABLE Passenger (
    Passenger_id INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT,
    Gender VARCHAR(10)
);
 Flight Table
CREATE TABLE Flight (
    Flight_id INT PRIMARY KEY,
    Flight_name VARCHAR(50),
    Source VARCHAR(50),
    Destination VARCHAR(50)
);
 Booking Table
CREATE TABLE Booking (
    Booking_id INT PRIMARY KEY,
    Passenger_id INT,
    Flight_id INT,
    Booking_date DATE,
    
    FOREIGN KEY (Passenger_id) REFERENCES Passenger(Passenger_id),
    FOREIGN KEY (Flight_id) REFERENCES Flight(Flight_id)
);
 Payment_Mode Table (Normalization Fix)
CREATE TABLE Payment_Mode (
    Payment_mode_id INT PRIMARY KEY,
    Mode_name VARCHAR(30)
);
 Payment Table
CREATE TABLE Payment (
    Payment_id INT PRIMARY KEY,
    Booking_id INT,
    Amount DECIMAL(10,2),
    Payment_mode_id INT,
    
    FOREIGN KEY (Booking_id) REFERENCES Booking(Booking_id),
    FOREIGN KEY (Payment_mode_id) REFERENCES Payment_Mode(Payment_mode_id)
);
