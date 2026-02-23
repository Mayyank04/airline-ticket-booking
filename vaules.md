-- 1. Airport
INSERT INTO Airport (AirportName, City, Country, IATACode) VALUES
('Indira Gandhi International Airport', 'Delhi', 'India', 'DEL'),
('Chhatrapati Shivaji Maharaj International Airport', 'Mumbai', 'India', 'BOM'),
('Kempegowda International Airport', 'Bangalore', 'India', 'BLR');

-- 2. Aircraft
INSERT INTO Aircraft (Model, Capacity) VALUES
('Airbus A320', 180),
('Boeing 737', 160);

-- 3. Staff
INSERT INTO Staff (Name, Role, Phone) VALUES
('Amit Verma', 'Manager', '9000000001'),
('Neha Singh', 'Supervisor', '9000000002');

-- 4. Flight
INSERT INTO Flight (FlightNumber, SourceAirportID, DestinationAirportID, AircraftID, Duration) VALUES
('AI101', 1, 2, 1, 120),  -- Delhi to Mumbai
('AI202', 2, 3, 2, 105);  -- Mumbai to Bangalore

-- 5. Flight_Schedule
INSERT INTO Flight_Schedule (FlightID, DepartureDateTime, ArrivalDateTime, Status, StaffID) VALUES
(1, '2026-03-01 09:00:00', '2026-03-01 11:00:00', 'Scheduled', 1),
(2, '2026-03-01 14:00:00', '2026-03-01 15:45:00', 'Scheduled', 2);

-- 6. Seat
INSERT INTO Seat (AircraftID, SeatNumber, Class) VALUES
(1, '1A', 'Business'),
(1, '1B', 'Business'),
(1, '10A', 'Economy'),
(2, '1A', 'Business'),
(2, '12C', 'Economy');

-- 7. Customer
INSERT INTO Customer (FirstName, LastName, Email, Phone, PassportNumber) VALUES
('Rahul', 'Sharma', 'rahul@gmail.com', '9999999999', 'P1234567'),
('Priya', 'Verma', 'priya@gmail.com', '8888888888', 'P7654321');

-- 8. Booking
INSERT INTO Booking (CustomerID, BookingDate, Status) VALUES
(1, '2026-02-20', 'Confirmed'),
(2, '2026-02-21', 'Pending');

-- 9. Ticket
INSERT INTO Ticket (BookingID, ScheduleID, SeatID, Price) VALUES
(1, 1, 1, 5500.00),  -- Rahul booked seat 1A on schedule 1
(2, 2, 4, 4800.00);  -- Priya booked seat 1A on schedule 2

-- 10. Payment
INSERT INTO Payment (BookingID, PaymentDate, Amount, Method, Status) VALUES
(1, '2026-02-20 10:30:00', 5500.00, 'Card', 'Success'),
(2, '2026-02-21 11:00:00', 4800.00, 'UPI', 'Pending');