# Movie-Ticket-Booking-sql-project
#move Ticket booking management system
A Movie Ticket Booking System developed using SQL to manage movie details, theaters, showtimes, seat availability, and ticket bookings. This project demonstrates database design, relational modeling, constraints, and query operations for a real-world booking system.

# Project Overview

The Movie Ticket Booking System allows users to:

View available movies

Check show timings

Select seats

Book tickets

Store payment information

# Database Structure
📂 Main Tables

Users – Stores customer details

Movies – Movie information (title, genre, duration, rating)

Theaters – Theater details

Screens – Screens inside theaters

Seats – Seat layout for each screen

Shows – Scheduled movie shows

Bookings – Ticket booking records

Payments – Payment transaction details

#Movie-Ticket-Booking-System/
│
├── schema.sql          # Database schema (CREATE TABLE statements)
├── insert_data.sql     # Sample data
├── queries.sql         # Important queries & reports
├── procedures.sql      # Stored procedures (if included)
├── triggers.sql        # Triggers (if included)
└── README.md
#🔄 System Workflow

Admin adds movies and theaters

Shows are scheduled

Users register/login

User selects movie and show

Available seats are displayed

Booking is confirmed

Payment is recorded

Seat status is updated

#Advantages of Movie Ticket Booking System
✅ 1. Easy Ticket Booking

Users can book tickets online without standing in long queues.

✅ 2. Time Saving

Reduces manual work and speeds up the booking process.

✅ 3. Accurate Seat Management

Prevents double booking using database constraints and seat status updates.

✅ 4. Centralized Data Management

All movies, users, bookings, and payments are stored in a structured database.

✅ 5. Real-Time Availability

Users can check available seats instantly.

✅ 6. Secure Data Storage

User and payment data can be protected using authentication and database security.

✅ 7. Automated Reports

Generates reports like:

Total revenue

Most popular movie

Booking history

Daily/Monthly sales

✅ 8. Scalable System

Can be expanded to:

Multiple cities

Multiple theaters

Mobile applications

✅ 9. Reduces Human Errors

Automation reduces mistakes in booking and billing.

✅ 10. Educational Value

Helps students understand:

Database design

ER modeling

SQL queries

Normalization

Real-world system implementation

#❌ Disadvantages of Movie Ticket Booking System
❌ 1. Requires Internet Access

  Users must have internet connectivity for online booking.

  ❌ 2. Initial Development Cost

   System setup and development may require time and resources.

  ❌ 3. Security Risks

  If not properly secured, it may face:

  SQL injection attacks

  Data breaches

    Step 1:Create database
  create database Movie-Ticket-Booking-project;

    Step 2:use database
---------------------
  Step 3:create table users
      
      create table users (
     User _id int primary key,
     name VARCHAR (100),
    email VARCHAR (100) UNIQUE,
     password VARCHAR (100)
     );
  Step 4:create table movie
  
     create table movies (
     movie _id int primary key,
     title varchar (50),
     duration int
    );
   step 5:create table shows 
   
    Create table shows ( 
    Show _id int primary key ,
    Movie _id INT,
    Show _date DATE 
    Show _time time ,
    price DECIMAL (6,2), 
    FOREIGN KEY (movie_ id) REFERENCES movies (movie _id) 
     );
--Step 6:create table seats 

      create tables seats ( 
    seat _id int primary kay,
    seat _number VARCHAR (10) 
    );
--Step 7:create table booking

    create table bookings (
    booking _id int primary key,
     user _id int,
     show _id int,
     seat _id int,
    booking _time datetime,
     foreign key (user_ id) references users (user _id),
     foreign key (show _id) references shows (show_ id),
    foreign key (seat _id) references seats (seat _id)
    ):
--step 8:insert values into user tabe

    insert into users (user _id, name, email, password) values
    (101, 'Sree Charani', 'charani@gmail.com', 'password12'),
     (102, 'Bob Smith', 'bob@gmail.com', 'password24'),
    (103, 'Richa Ghosh', 'ghosh@gmail.com', 'password35'),
    (104, 'Diana Green', 'diana@gmail.com', 'password49'),
    (105, 'Evan Miller', 'evan@gmail.com', 'password58'),
    (106, 'Sneh rana', 'rana@gmail.com', 'password69'),
    (107, 'Amanjot Kaur', 'kaur@gmail.com', 'password77'),
    (108, 'Harleen Deol', 'deol@gmail.com', 'password80'),
     (109, 'Deepti Sharma', 'sharma@gmail.com', 'password90'),
    (110, 'Sayali Satghare', 'satghare@gmail.com', 'password10');
--step 9:insert values into movies table

    Insert into movies (movie _id, title, duration) values
    (101, 'ram aur Shyam', 136),
    (102, 'Dilwale Dulhania ', 108),
    (103, 'Dil Chahta Hai', 169),
    (104, ' om shanti om', 175),
    (105, 'a few good men', 104),
    (106, 'back to the future', 182),
    (107, 'the godfather ', 142),
     (108, 'the wizard of oz', 189),
    (109, 'the lord of the rings', 155),
     (110, 'silence of the lambs', 195);
--step 9:insert values into shows table

    insert into shows (show _id, movie _id, show _date, show _time, price) values
    (111, 101, '2025-01-01', '10:00:00', 100.00),
    (112, 102, '2025-01-01', '13:00:00', 150.00),
    (134, 103, '2025-01-02', '15:00:00', 142.00),
    (154, 104, '2025-01-02', '18:00:00', 155.00),
    (156, 105, '2025-01-03', '11:00:00', 151.00),
    (164, 106, '2025-01-03', '14:00:00', 145.00),
    (174, 107, '2025-01-04', '16:00:00', 143.50),
    (185, 108, '2025-01-04', '19:00:00', 143.50),
    (195, 109, '2025-01-05', '12:30:00', 154.00),
     (110, 110, '2025-01-05', '17:00:00', 159.00);
--step 10:insert values into shows table

    insert into seats (seat_ id, seat _number) values
    (1011,'k1'),
    (1022,'k2'),
    (1033,'k3'),
    (1044,'k4'),
    (1055,'k5'),
    (1066,'k6'),
    (1077,'k7'),
    (1088,'k8'),
    (1099,'k9'),
    (1160,'k10');
 --step 11:insert values into booking table
 
    insert into bookings (booking _id, user _id, show _id, seat _id, booking _time) values
    (1011, 101, 110, 1011, '2025-01-01 10:00:00'),
    (1021, 102, 111, 1022, '2025-01-02 11:00:00'),
    (1031, 103, 112, 1033, '2025-01-03 12:00:00'),
    (1041, 104, 134, 1044, '2025-01-04 13:00:00'),
    (1051, 105, 154, 1055, '2025-01-05 14:00:00'),
    (1061, 106, 156, 1066, '2025-01-06 15:00:00'),
    (1071, 107, 164, 1077, '2025-01-07 16:00:00'),
    (1081, 108, 174, 1088, '2025-01-08 17:00:00'),
    (1091, 109, 185, 1099, '2025-01-09 18:00:00'),
    (1101, 110, 195, 1160, '2025-01-10 19:00:00');

1️⃣ Display all users

        SELECT * FROM users;

2️⃣ List all movies

    SELECT * FROM movies;

3️⃣ Display all available shows

     SELECT * FROM shows
    WHERE show_date >= CURDATE();

4️⃣ Fetch movie details using movie_id

    SELECT * FROM movies
    WHERE movie_id = 1;

5️⃣ List all shows of a particular movie

    SELECT * FROM shows
    WHERE movie_id = 1;

6️⃣ List all seat numbers

    SELECT seat_number FROM seats;

7️⃣ Find available seats for a specific show

    SELECT s.seat_id, s.seat_number
    FROM seats s
    WHERE s.seat_id NOT IN (
    SELECT bs.seat_id
    FROM booking_seats bs
    JOIN bookings b ON bs.booking_id = b.booking_id
    WHERE b.show_id = 1
    );

8️⃣ Display booked seats for a specific show

     SELECT s.seat_number
     FROM seats s
     JOIN booking_seats bs ON s.seat_id = bs.seat_id
      JOIN bookings b ON bs.booking_id = b.booking_id
    WHERE b.show_id = 1;

9️⃣ Insert a new user

    INSERT INTO users (name, email, phone, password)
    VALUES ('John Doe', 'john@example.com', '9876543210', 'password123');

🔟 Insert a new movie

    INSERT INTO movies (title, genre, duration, language, rating)
     VALUES ('Inception', 'Sci-Fi', 148, 'English', 'PG-13');

1️⃣1️⃣ Insert a new show

    INSERT INTO shows (movie_id, screen_id, show_date, show_time, price)
    VALUES (1, 1, '2026-02-15', '18:30:00', 250);

1️⃣2️⃣ Add a new seat

       INSERT INTO seats (screen_id, seat_number, seat_type)
     VALUES (1, 'A10', 'Regular');

1️⃣3️⃣ Book a ticket for a user

  Step 1 – Insert booking:

    NSERT INTO bookings (user_id, show_id, booking_date, total_amount, status)
     VALUES (1, 1, NOW(), 250, 'Confirmed');


Step 2 – Assign seat:

           INSERT INTO booking_seats (booking_id, seat_id)
          VALUES (1, 5);

1️⃣4️⃣ Display all bookings

    SELECT * FROM bookings;

1️⃣5️⃣ Booking history for a specific user

      SELECT * FROM bookings
      WHERE user_id = 1;

1️⃣6️⃣ Count total bookings for a specific show

      SELECT COUNT(*) AS total_bookings
     FROM bookings
         WHERE show_id = 1;

1️⃣7️⃣ Count total bookings for a specific movie

      SELECT COUNT(*) AS total_bookings
        FROM bookings b
       JOIN shows s ON b.show_id = s.show_id
       WHERE s.movie_id = 1;

1️⃣8️⃣ Find movies of a specific genre

    SELECT * FROM movies
    WHERE genre = 'Action';

1️⃣9️⃣ Update movie duration

    UPDATE movies
     SET duration = 150
     WHERE movie_id = 1;

2️⃣0️⃣ Update seat number

      UPDATE seats
    SET seat_number = 'B12'
    WHERE seat_id = 5;

2️⃣1️⃣ Delete a specific booking

      DELETE FROM bookings
       WHERE booking_id = 1;

2️⃣2️⃣ Delete a movie

    DELETE FROM movies
    WHERE movie_id = 1;

2️⃣3️⃣ List movies longer than 2 hours (120 minutes)

        SELECT * FROM movies
       WHERE duration > 120;

2️⃣4️⃣ Find shows scheduled for today

       SELECT * FROM shows
        WHERE show_date = CURDATE();

2️⃣5️⃣ List upcoming shows sorted by date and time

     SELECT * FROM shows
    WHERE show_date >= CURDATE()
    ORDER BY show_date ASC, show_time ASC;



