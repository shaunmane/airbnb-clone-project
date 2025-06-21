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
**Important Fields**: 
- `user_id`(Primary Key)
- `name`
- `email`
- `role`(e.g., guest, host)

**Relationships**:
- Can own Properties 
- Can make Bookings 
- A user can write multiple reviews

### 2. Properties: Listings available for rent (e.g., apartments, houses).
**Important Fields**: 
- `property_id` (Primary Key)
- `title`
- `location`
- `price_per_night`

**Relationships**:
- Belongs to a User (host)
- Can have multiple Bookings
- Can receive multiple Reviews

### 3. Bookings: Reservation records linking users to properties.
**Important Fields**: 
- `booking_id` (Primary Key)
- `user_id` 
- `property_id` 
- `check_in`, `check_out`
- `status` (e.g., confirmed, cancelled)

**Relationships**:
- Links Users and Properties
- Each Booking can have one Payment

### 4. Reviews: Feedback from users about properties or hosts.
**Important Fields**: 
- `review_id` (Primary Key)
- `user_id`
- `property_id` 
- `rating`

**Relationships**:
- Submitted by Users
- Linked to Properties

### 5. Payments: Tracks financial transactions related to bookings.
**Important Fields**: 
- `payment_id`
- `booking_id` 
- `amount`
- `payment_method`
- `payment_date`

**Relationships**:
- Associated with a Booking
- Indirectly linked to a User and Property through the Booking

## Feature Breakdown

## API Security

## CI/CD Pipeline