# Airbnb Clone Project – Backend

This project is a simplified clone of Airbnb focused on backend development. It aims to simulate building a real-world booking platform using modern technologies.

## Project Goals

- Build RESTful APIs with Django
- Design a relational database using MySQL
- Implement API security (authentication & authorization)
- Use GitHub for team collaboration
- Set up CI/CD for automated testing and deployment

## Tech Stack

- Django
- MySQL
- Django REST Framework
- Docker
- GitHub Actions

## Team Roles

### Backend Developer  
Builds the application's core logic and RESTful APIs using Django. Responsible for implementing endpoints, handling server-side functionality, and ensuring data flows correctly between the frontend and the database.

### Database Administrator (DBA)  
Designs, manages, and optimizes the database (PostgreSQL or MySQL). Ensures data consistency, integrity, indexing, and handles backups or migrations.

### DevOps Engineer  
Manages deployment infrastructure, Docker setup, and CI/CD pipelines using tools like GitHub Actions. Ensures smooth integration, testing, and deployment of backend code.

### Security Engineer  
Implements API security measures such as authentication, authorization, input validation, and encryption. Protects the system against vulnerabilities and unauthorized access.

### QA Engineer  
Writes and runs tests for backend functionality. Ensures all APIs behave as expected, identifies bugs early, and maintains quality standards across all features.

### Documentation Lead  
Creates and maintains technical documentation including API specs, database diagrams, and setup instructions. Helps the team and future contributors understand the project structure and functionality.

## Technology Stack

### Django  
A high-level Python web framework used to build the backend logic and RESTful APIs for the application.

### Django REST Framework (DRF)  
An extension of Django that simplifies the creation of powerful and flexible REST APIs.

### PostgreSQL  
A reliable and scalable relational database system used to store and manage all structured data such as users, properties, bookings, and payments.

### GraphQL  
A query language that allows clients to request exactly the data they need, reducing over-fetching and under-fetching of information.

### Celery  
Handles background tasks like sending confirmation emails or processing asynchronous events such as payment notifications.

### Redis  
Used for caching and managing asynchronous task queues with Celery, helping improve application speed and responsiveness.

### Docker  
Containerizes the backend environment, ensuring consistency across development, testing, and production.

### GitHub Actions  
Automates testing and deployment processes, enabling continuous integration and continuous delivery (CI/CD).

## Database Design

The backend uses a relational database to store and manage data for the application. Key entities and their relationships are outlined below:

### 1. Users
- `id`: Unique identifier
- `username`: Unique name for login
- `email`: User's email address
- `password`: Encrypted password
- `is_host`: Boolean to check if user can list properties

### 2. Properties
- `id`: Unique identifier
- `owner_id`: Foreign key to Users
- `title`: Property name
- `description`: Property details
- `location`: Address or city

**Relation**: A user (host) can own multiple properties.

### 3. Bookings
- `id`: Unique identifier
- `user_id`: Foreign key to Users
- `property_id`: Foreign key to Properties
- `check_in`: Start date
- `check_out`: End date

**Relation**: A user can have many bookings; a booking belongs to one property.

### 4. Reviews
- `id`: Unique identifier
- `user_id`: Foreign key to Users
- `property_id`: Foreign key to Properties
- `rating`: Integer score
- `comment`: Text review

**Relation**: A user can leave multiple reviews; a property can have many reviews.

### 5. Payments
- `id`: Unique identifier
- `booking_id`: Foreign key to Bookings
- `amount`: Payment amount
- `status`: e.g., “completed”, “pending”
- `payment_date`: Timestamp

**Relation**: Each payment is linked to a booking.

## Feature Breakdown

### User Management  
Allows users to register, log in, and manage their profiles. Hosts can create and update property listings, while guests can manage their bookings and account settings.

### Property Management  
Enables hosts to add new listings, update details, or remove properties. Users can browse listings based on location, price, and availability.

### Booking System  
Provides functionality for users to book available properties. Includes features for selecting dates, confirming availability, and canceling bookings.

### Payment Integration  
Handles secure payment processing for bookings. Tracks payment status and generates payment records associated with each reservation.

### Review System  
Lets users rate and review properties after their stay. Helps maintain quality and trust between guests and hosts.

### API Documentation  
Uses OpenAPI and GraphQL to provide clear, structured documentation for all available endpoints and queries.

## API Security

To protect user data and ensure secure operations, the following security measures will be implemented:

- **Authentication**: Uses JWT or token-based authentication to ensure only registered users can access protected resources.
- **Authorization**: Ensures users can only perform actions allowed by their role (e.g., only hosts can edit listings).
- **Rate Limiting**: Prevents abuse of APIs by limiting the number of requests from a single user or IP.
- **Data Validation**: Sanitizes input to prevent injection attacks and ensure only valid data is stored.
- **HTTPS**: Encrypts all data in transit to protect user information and login credentials.

**Why It Matters**:
- **User Data Protection**: Secures sensitive data such as passwords, emails, and bookings.
- **Transaction Security**: Ensures payments are safe and tamper-proof.
- **System Stability**: Prevents spamming, scraping, and DoS attacks.

## CI/CD Pipeline

CI/CD (Continuous Integration and Continuous Deployment) automates the testing and deployment of code changes.

### Why It's Important:
- Speeds up development by catching bugs early
- Ensures reliable and consistent deployments
- Reduces manual effort and human error

### Tools Used:
- **GitHub Actions**: Automates running tests and deploying updates to staging/production.
- **Docker**: Packages the app in a consistent container for all environments.
- **pytest / unittest**: Used to run backend tests during the CI process.