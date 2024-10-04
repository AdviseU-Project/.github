# AdviseU - System Architecture

AdviseU is a web-based application designed to help students and advisors at Oregon State University (OSU) generate and optimize personalized course plans. This document outlines the system architecture of AdviseU, including the frontend, backend, data management, and third-party integration components.

## Table of Contents
- [Overview](#overview)
- [System Components](#system-components)
- [Frontend Architecture](#frontend-architecture)
- [Backend Architecture](#backend-architecture)
- [Database](#database)
- [APIs & Integration](#apis--integration)
- [Security & Authentication](#security--authentication)
- [Future Considerations](#future-considerations)

---

## Overview

The AdviseU system architecture is built around a modular approach, ensuring that each part of the system operates independently while remaining tightly integrated. The architecture supports scalability, high user activity during peak times (such as registration periods), and real-time data updates from OSU’s systems.

The primary architectural components are:
1. **Frontend**: The user-facing interface for students and advisors.
2. **Backend**: The server that processes requests, manages business logic, and integrates data from external systems.
3. **Database**: The storage for course data, degree plans, and user preferences.
4. **APIs**: The integration points for pulling course data, real-time availability, and student progress from OSU systems.
5. **Security**: Authentication and data protection mechanisms.

---

## System Components

### 1. **Frontend**
   - **Framework**: React (with TypeScript for type safety and scalability)
   - **Styling**: Tailwind CSS and DaisyUI for a responsive, modern UI
   - **Features**:
     - Course Planner (drag-and-drop interface for creating schedules)
     - Degree Progress Tracker
     - Course Search and Details
     - Term View (detailed view of planned courses for each term)

### 2. **Backend**
   - **Programming Language**: Go
   - **Features**:
     - Business logic to generate course schedules based on inputs (degree requirements, course availability, etc.)
     - API endpoints for frontend requests
     - Integration with OSU APIs for real-time course and student data
     - Handles updates to course plans and degree tracking

### 3. **Database**
   - **Type**: PostgreSQL (for relational data management)
   - **Data Entities**:
     - Courses (ID, title, description, credits, prerequisites)
     - Degree Programs (required courses, elective options)
     - User Data (student information, preferences, saved plans)
   - **Features**:
     - Stores course data, user preferences, and degree progress
     - Supports querying course availability, prerequisites, and scheduling data

### 4. **APIs**
   - **OSU Developer Portal APIs**: Integration with OSU systems.
   - **Custom APIs**: For handling user requests, updating degree plans, and integrating other OSU systems.

### 5. **Security**
   - **Authentication**: OAuth 2.0 for user authentication via OSU’s Single Sign-On (SSO) system.
   - **Role-based Access Control (RBAC)**: Ensures students, advisors, and administrators have access to appropriate features and data.
   - **Data Protection**: All data in transit is encrypted using HTTPS. Sensitive user data is encrypted at rest.

---

## Frontend Architecture

- **React Components**: The UI is built using reusable React components.
- **State Management**: Using React’s Context API and/or Redux for managing global state, particularly for course planning and user data.
- **Responsive Design**: The application will be fully responsive, eventually supporting both desktop and mobile devices.
- **Course Planning Logic**: The frontend handles user interaction and communicates with the backend to fetch course schedules and degree requirements.

---

## Backend Architecture

- **Go**: The backend manages the application’s logic, processes requests, and communicates with external APIs.
- **REST API**: The backend exposes RESTful endpoints for the frontend to fetch data such as courses, degree plans, and scheduling information.
- **Scheduling Algorithm**: A heuristic-based algorithm prioritizes degree-required courses, availability, and user preferences to generate course plans.
- **Data Processing**: The backend integrates with OSU APIs to pull and update course data dynamically.

---

## Database

- **PostgreSQL**: Used for relational data management, ensuring data consistency for courses, degrees, and user profiles.
- **Tables**:
  - `Courses`: Stores course information, including prerequisites, availability, and credits.
  - `Users`: Stores user-specific data such as degree programs, preferences, and saved plans.
  - `DegreePrograms`: Tracks various degree requirements, including options and minors.
- **Relationships**:
  - Each user has one or more saved course plans.
  - Courses have relationships with degree programs and prerequisites.
- **Data Versioning**: Ensures updates to course data do not affect previously generated plans unless explicitly refreshed by the user.

---

## APIs & Integration

- **[OSU Developer Portal APIs](https://developer.oregonstate.edu/apis)**
  - **[Academic Disciplines v1](https://developer.oregonstate.edu/api/8)**: Need to check out.
  - **[Terms v1](https://developer.oregonstate.edu/api/17)**: Need to check out.
- **Custom APIs**:
  - **Course Plan Generation**: Creates or updates a personalized course plan.
  - **Degree Progress Tracking**: Provides real-time updates on degree progress and course completion.
  - **Course Availability Checker**: Ensures up-to-date course schedules.
  
---

## Security & Authentication

- **OAuth 2.0**: For secure user authentication, integrated with OSU’s SSO system.
- **Role-based Access Control**: Defines different roles (students, advisors, admin) with varying levels of access.
- **Encryption**: All sensitive data is encrypted both in transit (via HTTPS) and at rest in the database.

---

## Future Considerations

As AdviseU evolves, the architecture will be adapted to include additional features and scalability improvements:

1. **Scaling**: Implement horizontal scaling for the backend to handle large user loads during registration periods.
2. **AI-powered Recommendations**: Integrating AI to provide students with course recommendations based on historical data and career goals.
3. **Caching**: Implementing caching mechanisms to reduce load times and API calls for frequently accessed data.
4. **Mobile App**: Developing a native mobile app that interacts with the same backend architecture.
5. **GraphQL**: Consider migrating to GraphQL to optimize data fetching and reduce over-fetching/under-fetching issues.

---

This system architecture provides a foundation for AdviseU, ensuring flexibility, scalability, and smooth integration with existing OSU systems. The next phases will focus on expanding functionality, improving user experience, and adding advanced features.
