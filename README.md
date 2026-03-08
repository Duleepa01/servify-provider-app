# Servify Provider App

The **Servify Provider App** is the mobile application used by service providers on the Servify platform to manage their services, view bookings, and track earnings.

This app is part of the **Servify service marketplace system**, which consists of three main components:

* Customer Android App
* Provider Android App
* Admin Web Panel

All components are connected through **Firebase backend services**.

---

## Overview

The Provider App allows registered service providers to:

* Create an account and register as a service provider
* Log in securely
* Wait for admin approval before accessing the platform
* View and manage assigned bookings
* Track earnings
* Manage their profile

The application communicates with the same Firebase backend used by the customer app and admin panel.

---

## Tech Stack

**Platform**

* Android (Java)

**Backend**

* Firebase Authentication
* Cloud Firestore

**Design**

* Material Design 3

**Development Environment**

* Android Studio

---

## Core Features

### Authentication

* Provider registration
* Secure login using Firebase Authentication
* Admin approval check before allowing dashboard access

### Provider Dashboard

* Overview of provider activity
* Quick access to bookings and earnings

### Booking Management

* View assigned customer bookings
* Track job status

### Earnings Tracking

* Monitor completed service payments

### Profile Management

* Update provider details
* View account information

---

## Project Structure

```
app/
 ├── java/com/servify/provider
 │    ├── activities
 │    ├── fragments
 │    ├── adapters
 │    ├── models
 │    └── utils
 │
 ├── res
 │    ├── layout
 │    ├── drawable
 │    ├── values
 │
 └── AndroidManifest.xml
```

---

## Firebase Database Structure (Simplified)

```
users
   uid
      name
      email
      phone
      role
      approved
      createdAt

bookings
   bookingId
      customerId
      providerId
      serviceId
      status
      date

services
   serviceId
      name
      category
      providerId
```

---

## Provider Registration Flow

1. Provider creates an account
2. Account data is stored in Firestore with role = `provider`
3. Account status is set to `approved = false`
4. Admin reviews the account through the Admin Panel
5. Once approved, the provider can access the dashboard

---

## System Architecture

```
Servify Platform

Customer App (Android)
        ↓
Firebase Backend
        ↓
Provider App (Android)
        ↓
Admin Panel (Web)
```

All components share the same Firebase project.

---

## Setup Instructions

1. Clone the repository

```
git clone https://github.com/YOUR_USERNAME/servify-provider-app.git
```

2. Open the project in Android Studio

3. Add your Firebase configuration file:

```
app/google-services.json
```

4. Sync Gradle and run the application.

---

## Current Development Status

The project is currently under development.
Core authentication and UI structures are being implemented.

Upcoming features include:

* Booking management
* Real-time booking updates
* Earnings analytics
* Push notifications
* Profile customization

---

## Related Repositories

Servify Platform includes multiple repositories:

* Servify Customer App
* Servify Provider App
* Servify Admin Panel

---

## License

This project is developed as part of an academic project and is intended for educational purposes.
