# 📍 Proximity Ping

### Hotel & Restaurant Discovery and Reservation System in C

**Proximity Ping** is a console-based location and hospitality management application developed in **C**. It allows users to explore restaurants and hotels across different areas, search and filter restaurants, make reservations, select hotel rooms and additional services, and receive a final billing statement.

The project was built to apply fundamental and intermediate C programming concepts to a larger real-world application.

---

## ✨ Features

### 🔐 User Registration & Login

Proximity Ping includes a simple file-based authentication system.

Users can:

- Create credentials
- Store their username and password
- Log in before accessing the application
- Receive validation for incorrect credentials
- View masked password output

Credentials are stored locally using C file handling.

---

### 🍽️ Restaurant Discovery

The application contains information about multiple restaurants across different locations.

Each restaurant contains details such as:

- Restaurant name
- Location
- Meal type
- Opening timings
- Description
- Average price per person
- Rating
- Available seats
- Reserved seats
- Reservation code

Restaurant information is represented using a C `struct`, keeping related data organized together.

---

### 📋 View All Restaurants

Users can display the complete restaurant directory and view information about every available restaurant.

Example information displayed:

```text
Restaurant Name
Reservation Code
Meal Type
Description
Average Price
Rating
Timings
Address
```

---

### 🔎 Restaurant Search

Proximity Ping provides a case-insensitive search system.

Users can search using information such as:

```text
Restaurant Name
Location / Address
Description
```

The program converts strings to lowercase and performs substring matching, allowing searches to work without requiring exact capitalization.

---

### 🎯 Restaurant Filtering

Restaurants can be filtered according to user preferences.

#### Filter by Price

Users provide:

```text
Minimum Price
Maximum Price
```

Only restaurants within the specified price range are displayed.

#### Filter by Rating

Users can similarly provide:

```text
Minimum Rating
Maximum Rating
```

to find restaurants matching their preferred rating range.

---

### 🎟️ Restaurant Reservations

Users can make restaurant reservations directly through the program.

The system asks for:

```text
Reservation Code
Number of Seats
Reservation Name
```

Before confirming the reservation, the program checks whether enough seats remain available.

If successful, the reservation count is updated and the remaining seats are displayed.

---

## 🏨 Hotel Discovery

Proximity Ping also provides information about hotels available across multiple areas.

Locations include:

```text
Civil Lines
PECHS
Clifton
Cantonment
Sector 14
Regal Chowk
Malir Cantt
Shah Latif
Shahrah-e-Faisal
North Nazimabad
```

Users can explore hotel information including:

- Ratings
- Services
- Dining availability
- Payment options
- Opening hours
- User reviews
- Proximity Ping discounts

---

## 🛏️ Hotel Booking System

After selecting a hotel, users can configure their stay through an interactive booking process.

### Room Types

The application supports options including:

```text
Single Room
├── Premium
├── VIP
└── Medium

Double Room
├── King and Queen
└── Family
```

Each selection contributes toward the final booking cost.

---

## 🍕 Food & Beverages

Hotel guests can select food and beverages from the built-in menu.

Available options include:

```text
Pizza
Burger
Pasta
Coke
Coffee
```

Selected items are stored and added to the customer's total bill.

---

## 🍳 Room Service

Users can also select meal services:

```text
Breakfast
Lunch
Dinner
Breakfast + Lunch + Dinner
```

The selected room service is recorded as part of the hotel booking.

---

## 🏊 Additional Hotel Facilities

Additional hotel services are available, including:

```text
🚗 Parking
💆 SPA
🏊 Swimming Pool
🏋️ Fitness Centre
💼 Business Centre
```

Selected services are tracked and their costs are added to the total bill.

---

## 🧾 Final Billing System

At the end of the hotel booking process, Proximity Ping generates a billing summary.

Example:

```text
************ Final Billing Statement ************

Username: User
Hotel Name: Selected Hotel

Room Type: Double
Room Class: Family

Additional Facilities:
- Parking
- Swimming Pool

Restaurant Facilities:
- Pizza
- Coffee

Total Cost: XXXX
```

The bill combines the selected room, food, room services, and additional facilities.

---

## ⏳ Loading Animation

The program includes a console-based progress bar when transitioning into the hotel or restaurant system.

```text
ID 527 : [==============================          ] 75%
```

A random session-style ID is generated to accompany the loading animation.

---

# 🧠 C Programming Concepts Demonstrated

This project combines several important C programming concepts.

### Structures

Restaurant and billing information is organized using structures:

```c
struct ResturantDetails {
    char Name[MAX_NAME_LEN];
    char mealType[MAX_NAME_LEN];
    char Timings[MAX_NAME_LEN];
    char Desc[200];
    char address[50];
    float price;
    float rating;
    int area;
    int availableSeats;
    int reservedSeats;
};
```

---

### Dynamic Memory Allocation

Memory for user credentials is allocated dynamically using:

```c
malloc()
```

and released using:

```c
free()
```

This demonstrates basic **heap memory management**.

---

### File Handling

The application uses files for credential storage and authentication.

Important operations include:

```c
fopen()
fprintf()
fscanf()
fclose()
```

---

### String Manipulation

The project makes extensive use of C string functions, including:

```c
strcmp()
strcpy()
strlen()
strstr()
strcspn()
tolower()
```

These are used for authentication, searching, hotel selection, and text processing.

---

### Arrays

Arrays are used to manage:

- Restaurant records
- Hotel names
- Locations
- Selected services
- Food selections
- User input

---

### Functions

The program is divided into dedicated functions for different responsibilities.

Examples include:

```c
DisplayAll()
DisplayResturant()
Filter()
Search()
makeReservation()
Resturantmenu()
hotel()
func()
```

This helps separate the major features of the application.

---

### Pointers

Pointers are used alongside dynamically allocated memory for storing and managing user credentials.

---

### Loops & Conditional Logic

The application makes extensive use of:

```c
for
while
if / else
switch
```

to implement interactive menus, searching, validation, reservations, hotel services, and billing.

---

## 🏗️ Program Architecture

```text
                    ┌─────────────────────┐
                    │   PROXIMITY PING    │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Register / Login    │
                    └──────────┬──────────┘
                               │
                               ▼
                     Hotel or Restaurant?
                       /              \
                      /                \
                     ▼                  ▼
          ┌──────────────────┐  ┌──────────────────┐
          │      HOTEL       │  │    RESTAURANT    │
          └────────┬─────────┘  └────────┬─────────┘
                   │                     │
             Select Location       Display Restaurants
                   │                     │
              Select Hotel          Search / Filter
                   │                     │
              Select Room            Reservation
                   │                     │
             Food & Services        Seat Validation
                   │
          Additional Facilities
                   │
                   ▼
              Final Billing
```

---

# 📂 Project Structure

A simple repository structure can be:

```text
Proximity-Ping/
│
├── main.c
├── creds.txt
└── README.md
```

`creds.txt` is generated/updated by the program to store login credentials.

> For a public repository, use dummy credentials only. Real passwords should never be committed to GitHub.

---

# 🚀 Getting Started

## Requirements

The project is written in **C** and uses Windows-specific functionality.

Recommended environment:

- Windows
- GCC / MinGW
- Visual Studio Code or another C-compatible IDE

---

## Clone the Repository

```bash
git clone <your-repository-url>
cd Proximity-Ping
```

---

## Compile

Using GCC:

```bash
gcc main.c -o proximity_ping
```

Run the application:

```bash
proximity_ping.exe
```

Depending on your compiler/environment, minor compatibility adjustments may be required because the source includes Windows-specific headers alongside `unistd.h`.

---

# 🎮 How to Use

After starting the program:

```text
1. Enter a username and password.
          ↓
2. Log in using your credentials.
          ↓
3. Choose HOTEL or RESTAURANT.
          ↓
4. Explore the selected service.
```

### Restaurant Path

```text
Restaurant
    │
    ├── Display All Restaurants
    │
    ├── Filter by Price / Rating
    │
    ├── Search
    │
    └── Make Reservation
```

### Hotel Path

```text
Hotel
  │
  ├── Select Location
  ├── View Hotel
  ├── Select Hotel
  ├── Choose Room
  ├── Select Food
  ├── Select Room Service
  ├── Select Additional Facilities
  └── Generate Final Bill
```

---

# 🔒 Security Note

The authentication implementation in this project is designed for demonstrating **C file handling and login logic**, not production authentication.

Credentials are stored locally in plain text.

A production application should instead use:

- Password hashing
- Salting
- Secure databases
- Proper authentication sessions
- Input validation
- Protected credential storage

---

# ⚠️ Current Limitations

The current implementation is primarily an academic console application.

Some limitations include:

- Local text-file credential storage
- Plain-text passwords
- Hard-coded hotel and restaurant data
- Console-only interface
- No database
- Reservations are not permanently stored
- Hotel pricing includes randomized cost ranges
- Platform-dependent functionality
- Limited input validation

---

# 🔮 Future Improvements

Potential improvements include:

- 🗄️ Database integration
- 🔐 Secure password hashing
- 👤 Persistent user accounts
- 🧾 Persistent reservation history
- 🗺️ Real location / maps integration
- 📍 Distance-based proximity calculations
- ⭐ User-generated ratings and reviews
- 💳 Payment simulation
- 📅 Date-based hotel bookings
- 🍽️ Restaurant table management
- 🏨 Hotel room availability tracking
- 🖥️ GUI or web interface
- 🌐 REST API backend
- 📊 Admin dashboard

---

# 🎯 Project Purpose

Proximity Ping was developed to apply C programming concepts in a larger application rather than isolated programming exercises.

The project combines:

```text
C Programming
      │
      ├── Structures
      ├── Arrays
      ├── Pointers
      ├── Dynamic Memory
      ├── File Handling
      ├── Searching
      ├── Filtering
      ├── String Processing
      ├── Functions
      └── Menu-Driven Programming
             │
             ▼
       PROXIMITY PING
             │
        ┌────┴────┐
        ▼         ▼
      Hotels   Restaurants
```

---

# 📚 What I Learned

Through this project, I gained practical experience with:

- Building a larger program in C
- Breaking functionality into functions
- Designing and using structures
- Managing arrays of structures
- Dynamic memory allocation
- Heap memory management
- File I/O
- Credential validation
- String manipulation
- Case-insensitive searching
- Range-based filtering
- Reservation logic
- Menu-driven program design
- Input handling
- Billing calculations
- Managing interconnected program features

---

# 👩‍💻 Author

**Aleeza**  
BS Computer Science — FAST-NUCES

---

## ⭐ About Proximity Ping

**Proximity Ping** demonstrates how fundamental C programming concepts can be combined into a complete interactive application covering hospitality discovery, restaurant reservations, hotel bookings, authentication, and billing.

It was developed as a practical programming project with an emphasis on **structured problem solving, data management, modular programming, and user interaction**.
