# Airbnb Clone Project - ProDev Back End
The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. It involves a deep dive into full-stack development, focusing on backend systems, database design, API development, and application security. This project enables learners to understand complex architectures, workflows, and collaborative team dynamics while building a scalable web application.

## Table of Content
- [Project Goals](#project-goals)
- [Team Roles](#team-roles)
- [Technology Stack](#technology-stack)
- [Database Design](#database-design)
- [Feature Breakdown](#feature-breakdown)
- [API Security](#api-security)
- [CI/CD Pipeline](#cicd-pipeline)

## Project Goals

1. **User Management**: Implement a secure system for user registration, authentication, and profile management.

2. **Property Management**: Develop features for property listing creation, updates, and retrieval.

3. **Booking System**: Create a booking mechanism for users to reserve properties and manage booking details.
    
4. **Payment Processing**: Integrate a payment system to handle transactions and record payment details.
    
5. **Review System**: Allow users to leave reviews and ratings for properties.
    
6. **Data Optimization**: Ensure efficient data retrieval and storage through database optimizations.


## Team Roles

**Business Analyst (BA)** - Analyzes stakeholder feedback to help a client formulate what their wants look like and align a customer’s vision with what a development team is producing.

**Product Owner (PO)** - Holds more responsibility for a product’s success than any other development team member for the product vision and evolution and makes sure the final product meets customer requirements

**Project Manager (PM)** - Oversees project scope, schedule, budget, and risk management; in Agile, collaborates closely with the PO to optimize delivery.

**UI/UX Designer** - Focuses on user journeys, usability testing, wireframes, and the product’s visual and interactive design.

**Software Architect** - Defines the system architecture and tech stack. Ensures scalability, performance, and maintainability.

**Software Developer** - Build and maintain the application’s functionality. Specializations include front-end, back-end, and mobile development.

**Quality Assurance (QA) Engineer** - Tests functionality, performance, and reliability. Uses manual and automated methods to ensure quality.

**Test Automation Engineer** - Develop test automation scripts—small programs that provide reliable and continuous feedback on application quality without any human involvement.

**DevOps Engineer** - Streamlines deployment and CI/CD pipelines, enabling faster release cycles and robust infrastructure. 


## Technology Stack

- **Django** - A high-level Python web framework used for building the RESTful API.

- **Django REST Framework** - Provides tools for creating and managing RESTful APIs.

- **PostgreSQL** - A powerful relational database used for data storage.
    
- **GraphQL** - Allows for flexible and efficient querying of data.
    
- **Celery** - For handling asynchronous tasks such as sending notifications or processing payments.
    
- **Redis** - Used for caching and session management.
    
- **Docker** - Containerization tool for consistent development and deployment environments.
    
- **CI/CD Pipelines** - Automated pipelines for testing and deploying code changes.

## Database Design

The key entities required for the project's database structure.

### 1. Users: Represents customers, hosts, and admins.
- `user_id`, `name`, `email`, `role`
- A user can own Properties, can make Bookings, can write multiple reviews.

### 2. Properties: Listings available for rent (e.g., apartments, houses).
- `property_id`, `title`, `location`, `price_per_night`
- Belongs to a User (host), can have multiple Bookings and receive multiple Reviews.

### 3. Bookings: Reservation records linking users to properties.
- `booking_id`, `user_id`, `property_id`, `check_in`, `check_out`, `status` (e.g., confirmed, cancelled)
- Links Users and Properties and each booking can have one Payment.

### 4. Reviews: Feedback from users about properties or hosts.
- `review_id`, `user_id`, `property_id`, `rating`
- Submitted by Users, linked to Properties.

### 5. Payments: Tracks financial transactions related to bookings.
- `payment_id`, `booking_id`, `amount`, `payment_method`, `payment_date`
- Associated with a booking and indirectly linked to a user and property through the booking.

## Feature Breakdown

- **API Documentation**: Documente APIs using the OpenAPI standard to ensure clarity and ease of integration.

- **User Management**: Allows users to register, log in, and manage their profile. Roles may include host or guest. 

- **Property Management**: Hosts can create, update, retrieve, and delete property listings.

- **Booking System**: Users can make, update, and manage bookings, including check-in and check-out details.

- **Payment Processing**: Handle payment transactions related to bookings.

- **Review System**: Post and manage reviews for properties.

- **Database Optimizations**: Use caching strategies to reduce database load and improve performance.

## API Security

Security is crucial to protect user data, ensure only authorized access, and safeguard financial transactions. Without strong security, user trust can be lost, data can be stolen, and the system can be exploited.

- **Authentication** - Verifies user identity using secure login methods and prevents unauthorized access to user accounts and personal data.

- **Authorization** - Ensures users can only access resources they're permitted to (e.g., only hosts can modify their listings).

- **Rate Limiting** - Prevents abuse of APIs by limiting the number of requests a user can make in a given timeframe.

- **Input Validation & Sanitization** - Maintains data integrity and protects application logic.

- **HTTPS & Data Encryption** - Encrypts all data in transit and optionally at rest (e.g., with TLS and AES).


## CI/CD Pipeline

CI/CD stands for Continuous Integration and Continuous Deployment (or Continuous Delivery). It's a set of practices and tools designed to improve the software development process by automating builds, testing, and deployment, enabling you to ship code changes faster and reliably.

- **Continuous integration (CI)** - refers to the practice of automatically and frequently integrating code changes into a shared source code repository.

- **Continuous delivery and/or deployment (CD)** - is a 2 part process that refers to the integration, testing, and delivery of code changes. 

  Continuous delivery stops short of automatic production deployment, while continuous deployment automatically releases the updates into the production environment.

### Tools That Could Be Used
- **GitHub Actions**: For CI/CD workflows (runs tests on every push/pull request).

- **Docker**: Containerization to ensure consistent environments across development/staging/production.

- **AWS/Heroku**: Cloud platforms for hosting the application.
