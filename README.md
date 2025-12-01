# Cab Hailing Application (C Language Project)

This project implements a complete Cab Hailing System in the C programming language. It models the essential operations of a real-world ride-hailing platform—including user registration, driver management, ride booking, driver assignment, and fare calculation—using only low-level programming constructs.

The application demonstrates strong proficiency in systems programming, modular C design, data structures, and file-based persistence. It serves as an academic project to showcase the ability to build functional systems from first principles and is suitable for inclusion in a Master's-level portfolio.

---

## 1. Project Overview

The Cab Hailing Application is a console-based system where users can book rides, drivers can accept or complete trips, and the application consistently updates all related records.

The core goals of the project are:
- To use **structured programming** and **modular decomposition** in C.
- To implement realistic operations using **structures**, **functions**, and **file I/O**.
- To simulate persistent storage using **text/binary files**.
- To demonstrate good program organization, input validation, and state handling.

The project avoids external libraries or frameworks, highlighting pure C programming ability.

---

## 2. Features

### User Operations
- Register new users
- Login using stored credentials
- Book a cab by entering pickup and destination
- View estimated fare
- Confirm or cancel booking
- View trip summary/history (if implemented)

### Driver Operations
- Register new drivers
- Login to the driver dashboard
- Mark themselves as available or busy
- View the most recent assigned ride
- Complete the trip and update the system

### Booking System
- Assigns the first available driver (or nearest driver, if location logic is implemented)
- Generates unique trip IDs
- Calculates fare based on distance or zone logic
- Stores trip details persistently

### Data Persistence
All records are stored using plain C file functions (`fopen`, `fprintf`, `fread`, etc.).  
Typical files include:
- `customer.txt`
- `driver.txt`
- `customer_advanced.txt`

---

## 3. Technical Design

### 3.1 Programming Paradigms
- Fully written in **ANSI C**
- Procedural and modular design
- Separation of tasks into multiple `.c` and `.h` files
- Structure-based data representation

### 3.2 Data Structures

Example structures:

```c
typedef struct {
    int id;
    char name[50];
    char phone[15];
} User;

typedef struct {
    int id;
    char name[50];
    int available;  // 1 = available, 0 = busy
} Driver;

typedef struct {
    int tripId;
    int userId;
    int driverId;
    char pickup[50];
    char drop[50];
    float fare;
    int status;     // 0 = booked, 1 = completed
} Trip;
```
### 3.3 File Handling Approach
- Uses standard C file operations: fopen, fclose, fprintf, fscanf, fread, fwrite  
- Sequential search for login, driver selection, and trip updates  
- Temporary-file method used for safe in-place updates  
- Transparent, human-readable text files for easier debugging and validation  

### 3.4 Algorithms Implemented
- Linear search for user/driver lookup  
- First-available-driver matching algorithm  
- Trip state machine:
  - 0 = booked
  - 1 = completed
- Fare calculation algorithm (distance-based or zone-based)
- Input validation and error-checking routines  


### Repository Structure

```
/ (root)
├── cproject.c
├── customer.txt
├── customer_advanced.txt
├── driver.txt
└── README.md
```

