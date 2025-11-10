# Edulance — Functional Document

## Overview
This document outlines the key features, requirements, and data flow of **Edulance**.  
The platform enables users to create or join hackathons and group projects.  
Each user can securely log in, post collaboration opportunities, and find teammates based on relevant skills and project requirements.

---

## Core Features

### Authentication
If a user is not registered, they can create an account by providing a **username**, **email**, and **password**.  
After registration, a verification email is sent to the provided email address.  
Once the user verifies their email, the account becomes active, allowing them to access the platform.

If the user is already registered, they can log in using their credentials.  
Upon successful authentication, they are redirected to the **Home Page**.  
If the credentials are invalid, an error message prompts them to re-enter their information.

![Authentication Flow](images/image.png)

---

### Authorization
Authorization in **Edulance** is role-based, granting different permissions to **Admins** and **Users**.

#### Admin Capabilities
- Can add or remove any user  
- Can add, remove, or update skills  
- Can update or delete any post  

#### User Capabilities
- Can create, update, or delete their own posts  
- Can join available posts created by others  
- Can view applicants for their posts  
- Can connect with other users via email  

![Authorization Roles](images/image2.png)

---

## In Scope

- **Account Management:** Users can register and log in.  
- **Authentication and Authorization:** JWT-based authentication with role-based access control (Admin and User roles).  
- **Post Creation and Management:** Users can create, update, and delete posts for hackathons or group projects, specifying the number of required participants, description, required skills, and application deadline.  
- **Skill Tagging:** Posts can include specific skills to attract suitable applicants.  
- **Application System:** Authenticated users can apply to open posts before the application deadline.  
- **Admin Management:** Admins can manage users, posts, and skills through the Django admin interface.

---

## Out of Scope

- Forgot Password feature  
- Rejecting or approving applications (no status tracking)  
- Sending direct messages or notifications between users  
- Commenting or asking questions on posts  
- Team creation and management after application acceptance  

---

## Requirements

### Functional Requirements

1. **User Authentication:** Users should be able to register, log in, and authenticate using JWT tokens.  
2. **Email Verification:** Upon registration, users must verify their email before accessing the platform.  
3. **Role-Based Access:** Admins have elevated permissions to manage users, skills, and posts.  
4. **Post Creation:** Authenticated users can create posts for hackathons or group projects.  
5. **Skill Management:** Admins can create and manage skills used in posts.  
6. **Application Submission:** Authenticated users can apply to open posts before deadlines.  
7. **Deadline Validation:** The system should automatically prevent applications after the last date.

---

### Technical Requirements

#### Backend
- **Framework:** Django with Django REST Framework (DRF) for REST APIs  
- **Language:** Python  
- **Authentication:** JWT-based authentication with email verification  
- **Email Verification:** Implemented via Django’s email backend to send verification links to users during registration  
- **Database:** PostgreSQL  
- **Validation:** Model and serializer-level input validation  
- **Testing:** Pytest for backend testing  
- **Environment Management:** `uv` for virtual environment and dependency management  
- **Deployment:** Docker support with environment configuration files (`.env`)

#### Frontend
- **Technologies:** HTML, CSS, JavaScript  
- **Framework:** Bootstrap  
