# Hotel-Management
# 🏨 Hotel Reservation and Management System

## 📖 Project Description

The Hotel Reservation and Management System is a relational database project designed to manage hotel operations efficiently. It allows hotel staff to manage guests, rooms, reservations, payments, and stays while maintaining data integrity through relational constraints.

This project was developed using SQL and follows database design principles including business rules, functional dependencies, and logical data modeling.

---

## 🎯 Objectives

* Manage guest information.
* Organize room categories and room availability.
* Handle room reservations.
* Track payments associated with reservations.
* Record guest stays (check-in and check-out).
* Maintain consistency and integrity of hotel data.

---

## 🗄️ Database Structure

### 1. Guest

Stores customer information.

| Field        | Type         |
| ------------ | ------------ |
| guest_id     | INT (PK)     |
| first_name   | VARCHAR(50)  |
| last_name    | VARCHAR(50)  |
| email        | VARCHAR(100) |
| phone_number | VARCHAR(20)  |
| address      | VARCHAR(255) |

---

### 2. Room Category

Defines room types and pricing.

| Field         | Type          |
| ------------- | ------------- |
| category_id   | INT (PK)      |
| category_name | VARCHAR(50)   |
| nightly_rate  | DECIMAL(10,2) |

---

### 3. Room

Stores room information.

| Field               | Type        |
| ------------------- | ----------- |
| room_id             | INT (PK)    |
| room_number         | VARCHAR(10) |
| floor               | INT         |
| availability_status | ENUM        |
| category_id         | INT (FK)    |

---

### 4. Booking

Manages reservations.

| Field          | Type     |
| -------------- | -------- |
| booking_id     | INT (PK) |
| booking_date   | DATE     |
| arrival_date   | DATE     |
| departure_date | DATE     |
| booking_status | ENUM     |
| guest_id       | INT (FK) |
| room_id        | INT (FK) |

---

### 5. Payment

Stores payment information.

| Field          | Type          |
| -------------- | ------------- |
| payment_id     | INT (PK)      |
| payment_amount | DECIMAL(10,2) |
| payment_method | VARCHAR(50)   |
| payment_date   | DATE          |
| booking_id     | INT (FK)      |

---

### 6. Stay

Tracks guest stays.

| Field          | Type     |
| -------------- | -------- |
| stay_id        | INT (PK) |
| arrival_time   | DATETIME |
| departure_time | DATETIME |
| booking_id     | INT (FK) |

---

## 🔗 Relationships

* One Guest ➜ Many Bookings
* One Room ➜ Many Bookings
* One Room Category ➜ Many Rooms
* One Booking ➜ Many Payments
* One Booking ➜ One Stay

---

## 📋 Business Rules

* Each guest has a unique identifier.
* A guest can have multiple reservations.
* A room belongs to only one category.
* A reservation is linked to one guest and one room.
* A room cannot be reserved twice during the same period.
* A reservation may generate multiple payments.
* Check-in and check-out must respect reservation dates.
* A completed reservation creates a stay record.

---

## 🛠️ Technologies Used

* MySQL
* SQL DDL (CREATE TABLE)
* Relational Database Design

---

## 🚀 Installation

```sql
CREATE DATABASE hotel_management;
USE hotel_management;
```

Execute the SQL script provided in the project to create all tables and relationships.

---

## 👨‍💻 Author

Database project developed for learning and academic purposes.
