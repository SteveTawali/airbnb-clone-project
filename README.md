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