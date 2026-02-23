-- 1. Airport Table
CREATE TABLE Airport (
    AirportID INT PRIMARY KEY AUTO_INCREMENT,
    AirportName VARCHAR(100) NOT NULL,
    City VARCHAR(50) NOT NULL,
    Country VARCHAR(50) NOT NULL,
    IATACode CHAR(3) UNIQUE NOT NULL
);

-- 2. Aircraft Table
CREATE TABLE Aircraft (
    AircraftID INT PRIMARY KEY AUTO_INCREMENT,
    Model VARCHAR(50) NOT NULL,
    Capacity INT NOT NULL CHECK (Capacity > 0)
);

-- 3. Staff Table
CREATE TABLE Staff (
    StaffID INT PRIMARY KEY AUTO_INCREMENT,
    Name VARCHAR(100) NOT NULL,
    Role VARCHAR(50) NOT NULL,
    Phone VARCHAR(15)
);

-- 4. Flight Table
CREATE TABLE Flight (
    FlightID INT PRIMARY KEY AUTO_INCREMENT,
    FlightNumber VARCHAR(10) NOT NULL,
    SourceAirportID INT NOT NULL,
    DestinationAirportID INT NOT NULL,
    AircraftID INT NOT NULL,
    Duration INT, -- in minutes

    FOREIGN KEY (SourceAirportID) REFERENCES Airport(AirportID),
    FOREIGN KEY (DestinationAirportID) REFERENCES Airport(AirportID),
    FOREIGN KEY (AircraftID) REFERENCES Aircraft(AircraftID)
);

-- 5. Flight_Schedule Table
CREATE TABLE Flight_Schedule (
    ScheduleID INT PRIMARY KEY AUTO_INCREMENT,
    FlightID INT NOT NULL,
    DepartureDateTime DATETIME NOT NULL,
    ArrivalDateTime DATETIME NOT NULL,
    Status ENUM('Scheduled', 'Delayed', 'Cancelled') DEFAULT 'Scheduled',
    StaffID INT,

    FOREIGN KEY (FlightID) REFERENCES Flight(FlightID),
    FOREIGN KEY (StaffID) REFERENCES Staff(StaffID)
);

-- 6. Seat Table
CREATE TABLE Seat (
    SeatID INT PRIMARY KEY AUTO_INCREMENT,
    AircraftID INT NOT NULL,
    SeatNumber VARCHAR(5) NOT NULL,
    Class ENUM('Economy', 'Business', 'First') NOT NULL,

    FOREIGN KEY (AircraftID) REFERENCES Aircraft(AircraftID),
    UNIQUE (AircraftID, SeatNumber) -- same seat number can't repeat in same aircraft
);

-- 7. Customer Table
CREATE TABLE Customer (
    CustomerID INT PRIMARY KEY AUTO_INCREMENT,
    FirstName VARCHAR(50) NOT NULL,
    LastName VARCHAR(50) NOT NULL,
    Email VARCHAR(100) UNIQUE,
    Phone VARCHAR(15),
    PassportNumber VARCHAR(20) UNIQUE NOT NULL
);

-- 8. Booking Table
CREATE TABLE Booking (
    BookingID INT PRIMARY KEY AUTO_INCREMENT,
    CustomerID INT NOT NULL,
    BookingDate DATE NOT NULL,
    Status ENUM('Confirmed', 'Cancelled', 'Pending') DEFAULT 'Pending',

    FOREIGN KEY (CustomerID) REFERENCES Customer(CustomerID)
);

-- 9. Ticket Table
CREATE TABLE Ticket (
    TicketID INT PRIMARY KEY AUTO_INCREMENT,
    BookingID INT NOT NULL,
    ScheduleID INT NOT NULL,
    SeatID INT NOT NULL,
    Price DECIMAL(10,2) NOT NULL,

    FOREIGN KEY (BookingID) REFERENCES Booking(BookingID),
    FOREIGN KEY (ScheduleID) REFERENCES Flight_Schedule(ScheduleID),
    FOREIGN KEY (SeatID) REFERENCES Seat(SeatID),
    UNIQUE (ScheduleID, SeatID) -- one seat can't be booked twice for same schedule
);

-- 10. Payment Table
CREATE TABLE Payment (
    PaymentID INT PRIMARY KEY AUTO_INCREMENT,
    BookingID INT NOT NULL,
    PaymentDate DATETIME NOT NULL,
    Amount DECIMAL(10,2) NOT NULL,
    Method ENUM('Card', 'UPI', 'NetBanking', 'Cash') NOT NULL,
    Status ENUM('Success', 'Failed', 'Pending') DEFAULT 'Pending',

    FOREIGN KEY (BookingID) REFERENCES Booking(BookingID)
);


