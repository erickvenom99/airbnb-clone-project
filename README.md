# Overview of Airbnb Clone

##  Objective
The backend for the Airbnb Clone project is designed to provide robust and scalable functionality that manages user interactions, search and discovery with advanced search filters (location, price, amenities, date, etc.), property listings, bookings, and payments.  
This backend supports various features required to mimic the core functionalities of Airbnb, ensuring a secure application and a smooth experience for users and hosts.

---

## Project Goals

- User Management: Implement a secure system for user registration, authentication, and profile management.  
- Property Management: Develop features for property listing creation, updates, and retrieval.  
- Booking System: Create a booking mechanism for users to reserve properties and manage booking details.  
- Payment Processing: Integrate a payment system to handle transactions and record payment details.  
- Review System: Allow users to leave reviews and ratings for properties.  
- Data Optimization: Ensure efficient data retrieval and storage through database optimization.

---

## Technology Stack

- Django: High-level Python web framework used for building the RESTful API.  
- Django REST Framework: Tools for creating and managing RESTful APIs.  
- PostgreSQL: Relational database used for data storage.  
- GraphQL: Enables flexible and efficient data querying.  
- Celery: Handles asynchronous tasks such as notifications or payment processing.  
- Redis: Used for caching and session management.  
- Docker: Provides containerization for consistent development and deployment.  
- CI/CD Pipelines:Automates testing and deployment of code changes.

---

##  Team Roles

### Backend Developer
Responsible for implementing API endpoints, database schemas, and business logic.  
Can also be involved in application architecture and integration.

### Database Administrator
Handles:
- Data security and access control (roles, permissions, encryption)
- Database design, indexing, backups, and optimization
- Documentation of configurations, changes, and incidents for performance reviews

### DevOps Engineer
Manages deployment, monitoring, and scaling of backend services.  
Ensures collaboration between development and operations teams.  
Builds pipelines for CI/CD (Continuous Integration & Continuous Delivery) to speed up release cycles.

##  Database Design

### Key Entities
- Users  
- Properties  
- Bookings  
- Reviews  
- Payments

---

###  User Management (Authentication & Profiles)
| Field | Type | Description |
|-------|------|-------------|
| user_id | PK | Unique user identifier |
| email | String | User email address |
| password_hash | String | Encrypted password |
| first_name | String | User first name |
| is_host | Boolean | Whether the user is a host |

---

### Property Management (Listings)
| Field | Type | Description |
|-------|------|-------------|
| property_id | PK | Unique property identifier |
| host_user_id | FK | Reference to host user |
| title | String | Property title |
| daily_rate | Decimal | Price per night |
| max_guests | Integer | Maximum guests |
| location_city | String | City location |

---

###  Booking & Availability
| Field | Type | Description |
|-------|------|-------------|
| booking_id | PK | Unique booking identifier |
| guest_user_id | FK | Guest user reference |
| property_id | FK | Booked property reference |
| check_in_date | Date | Check-in date |
| total_price | Decimal | Total booking cost |

---

### Reviews and Transactions
| Field | Type | Description |
|-------|------|-------------|
| review_id | PK | Unique review identifier |
| user_id | FK | Reviewer user reference |
| property_id | FK | Property reviewed |
| rating | Integer (1–5) | Review rating |
| comment | Text | Review content |