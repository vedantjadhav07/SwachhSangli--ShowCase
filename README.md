# SwachhSangli (स्वच्छ सांगली)

### Smart Municipal Solid Waste Management & Real-Time Fleet Monitoring Platform

A smart municipal waste management platform designed for **Sangli-Miraj-Kupwad Municipal Corporation (SMKC)** to digitize sanitation operations, monitor garbage collection vehicles in real time, manage citizen complaints, and improve municipal waste collection efficiency through geospatial technology and intelligent fleet monitoring.

---

<div align="center">

![Project](https://img.shields.io/badge/Project-Smart_Municipal_Management-16A34A)
![Backend](https://img.shields.io/badge/Backend-Spring_Boot-6DB33F?logo=springboot)
![Frontend](https://img.shields.io/badge/Frontend-React-61DAFB?logo=react)
![Mobile](https://img.shields.io/badge/Mobile-React_Native-61DAFB?logo=react)
![Database](https://img.shields.io/badge/Database-PostgreSQL-4169E1?logo=postgresql)
![Geospatial](https://img.shields.io/badge/Geospatial-PostGIS-008080)
![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?logo=docker)
![AWS](https://img.shields.io/badge/Cloud-AWS_EC2-FF9900?logo=amazonaws)

</div>

---

## Table of Contents

- [Overview](#overview)
- [Problem Statement](#problem-statement)
- [Objectives](#objectives)
- [System Architecture](#system-architecture)
- [User Roles](#user-roles)
- [Key Features](#key-features)
- [Real-Time Vehicle Tracking](#real-time-vehicle-tracking)
- [Complaint Management Workflow](#complaint-management-workflow)
- [Technology Stack](#technology-stack)
- [Geospatial Technology](#geospatial-technology)
- [Security](#security)
- [Deployment Architecture](#deployment-architecture)
- [My Contributions](#my-contributions)
- [Future Scope](#future-scope)

---

## Overview

**SwachhSangli** is a smart municipal waste management and sanitation monitoring platform developed to modernize garbage collection and municipal operations across Sangli-Miraj-Kupwad.

The platform connects citizens, drivers, ward supervisors (Mukadams), Sanitary Inspectors, and administrators through a unified digital system.

It combines:

- Real-time vehicle tracking
- GPS-based fleet monitoring
- Citizen grievance reporting
- Digital complaint management
- Ward-level sanitation monitoring
- Route history and vehicle movement analysis
- Geospatial mapping
- Role-based dashboards
- Real-time operational updates

The goal is to make municipal waste collection more transparent, efficient, trackable, and data-driven.

---

## Problem Statement

Traditional municipal waste collection systems face several operational challenges:

- Lack of real-time visibility into garbage collection vehicles.
- Difficulty tracking whether vehicles follow their assigned routes.
- Delays in identifying and resolving garbage-related complaints.
- Manual coordination between drivers, supervisors, and municipal officials.
- Lack of centralized monitoring across wards.
- Limited historical data for analyzing vehicle movement and collection operations.
- Citizens have limited visibility into complaint status and collection progress.

SwachhSangli addresses these challenges by providing a centralized platform for fleet tracking, complaint handling, municipal coordination, and sanitation monitoring.

---

## Objectives

- Digitize municipal waste collection and sanitation operations.
- Provide real-time monitoring of garbage collection vehicles.
- Enable citizens to report garbage-related issues digitally.
- Improve complaint assignment, tracking, and resolution.
- Provide ward-level fleet and sanitation monitoring.
- Maintain vehicle route history and operational records.
- Improve coordination between drivers, Mukadams, Sanitary Inspectors, and administrators.
- Enable data-driven municipal decision-making.

---

## System Architecture

SwachhSangli follows a full-stack architecture with web, mobile, backend, database, mapping, and external telematics integrations.

```text
                   ┌──────────────────────────┐
                   │      CITIZENS            │
                   │     MOBILE APP           │
                   └────────────┬─────────────┘
                                │
                   ┌────────────▼────────────┐
                   │    DRIVER MOBILE APP    │
                   │     REACT NATIVE        │
                   └────────────┬────────────┘
                                │
                   ┌────────────▼────────────┐
                   │    ADMIN WEB APP        │
                   │    REACT + VITE         │
                   └────────────┬────────────┘
                                │
                      REST APIs / WebSocket
                                │
              ┌─────────────────▼────────────────┐
              │          BACKEND                 │
              │       SPRING BOOT                │
              │                                  │
              │ Authentication & RBAC            │
              │ Complaint Management             │
              │ Fleet Management                 │
              │ Vehicle Tracking                 │ 
              │ Route & Ward Management          │
              │ Notifications                    │
              └───────────────┬──────────────────┘
                              │
           ┌──────────────────┼────────────────────┐
           │                  │                    │
           ▼                  ▼                    ▼
    ┌──────────────┐   ┌──────────────┐    ┌─────────────┐
    │ PostgreSQL   │   │   PostGIS    │    │   Redis     │
    │  Database    │   │ Geospatial   │    │   Cache     │
    └──────────────┘   └──────────────┘    └─────────────┘
                              │
                              ▼
                 ┌────────────────────────┐
                 │  WIALON GPS TELEMATICS │
                 │  Vehicle GPS Data      │
                 └────────────────────────┘
```

---

## User Roles

The system supports multiple user roles with dedicated functionality and access control.

| Role | Responsibilities |
|---|---|
| **Administrator** | Manage users, vehicles, wards, staff, routes, schedules, and system operations. |
| **Sanitary Inspector (SI)** | Monitor ward-level sanitation, vehicle operations, complaints, and operational performance. |
| **Mukadam / Supervisor** | Coordinate drivers, vehicles, collection schedules, and ward operations. |
| **Driver** | View assigned vehicles, collection tasks, routes, and handle assigned complaints. |
| **Citizen** | Report garbage complaints, upload evidence, track complaint status, and access collection information. |

---

## Key Features

### 1. Real-Time Fleet Monitoring

- Monitor municipal garbage collection vehicles on an interactive map.
- Track vehicle locations using GPS telematics data.
- View live vehicle movement and fleet status.
- Monitor vehicles assigned to wards.
- View vehicle route history.
- Track vehicle operational activity.

### 2. Citizen Grievance Management

- Submit garbage-related complaints.
- Capture complaint location through geolocation.
- Upload photographic evidence.
- Track complaint status.
- Monitor complaint resolution.
- Maintain complaint history.

### 3. Ward Management

- Manage municipal wards and their boundaries.
- Associate staff, vehicles, drivers, and supervisors with wards.
- Monitor sanitation activities ward-wise.
- Visualize ward-related information on interactive maps.

### 4. Vehicle Management

- Maintain vehicle registration and operational records.
- Associate drivers with vehicles.
- Manage vehicle assignments.
- Monitor vehicle locations and movement.
- Maintain historical vehicle assignment and route information.

### 5. Driver Management

- Provide drivers with their assigned vehicles and operational details.
- Display collection schedules and assigned work.
- Support complaint handling.
- Track completed work and route history.

### 6. Mukadam Dashboard

- Monitor ward-level vehicles and drivers.
- Manage assigned operational activities.
- Track complaint assignments and resolution.
- Monitor live vehicle locations.
- Access route history and fleet information.

### 7. Sanitary Inspector Dashboard

- Monitor sanitation operations across assigned wards.
- Track vehicle operations and complaint status.
- View ward-level performance.
- Monitor operational activities and pending grievances.

### 8. Admin Dashboard & Analytics

- Centralized municipal management dashboard.
- Manage personnel, vehicles, wards, and schedules.
- Monitor complaint statistics.
- Analyze fleet operations and sanitation activities.
- Track operational status across the system.

### 9. Real-Time Updates

- Live vehicle location updates.
- Real-time complaint status changes.
- WebSocket-based communication.
- Dynamic dashboard updates without repeatedly refreshing the page.

### 10. Multilingual Support

- Support for multiple languages in the municipal interface.
- Language selection for users.
- Localized interface content to improve accessibility for citizens and municipal staff.

---

## Real-Time Vehicle Tracking

Vehicle tracking is one of the core functionalities of SwachhSangli.

The system integrates vehicle GPS data from **Wialon telematics** to monitor municipal garbage collection vehicles.

### Tracking Workflow

```text
GPS Tracking Device Installed in Vehicle
                 │
                 ▼
          GPS Coordinates
          (Latitude, Longitude)
                 │
                 ▼
        Wialon Telematics Platform
                 │
                 ▼
        Vehicle Tracking API
                 │
                 ▼
        SwachhSangli Backend
                 │
         ┌───────┴────────┐
         │                │
         ▼                ▼
   Store Location    WebSocket Events
   & Route History         │
                          ▼
                  Admin / Mobile Apps
                          │
                          ▼
               Live Vehicle Map Display
```

### Tracking Capabilities

- GPS-based vehicle location monitoring.
- Live vehicle positions on maps.
- Vehicle movement visualization.
- Historical route playback.
- Ward-based vehicle monitoring.
- Vehicle location data processing.
- Real-time location broadcasting.

---

## Complaint Management Workflow

Citizens can report garbage-related issues directly through the mobile application.

### Complaint Lifecycle

```text
       CITIZEN REPORT
             │
             ▼
      COMPLAINT CREATED
             │
             ▼
        ASSIGNED TO
      DRIVER / VEHICLE
             │
             ▼
         IN PROGRESS
             │
             ▼
      ISSUE RESOLVED
     (Proof / Photograph)
             │
             ▼
         CLOSED
```

### Complaint Statuses

| Status | Description |
|---|---|
| **OPEN** | A new complaint has been submitted. |
| **ASSIGNED** | The complaint has been assigned to responsible personnel. |
| **IN_PROGRESS** | Work has started on the complaint. |
| **RESOLVED** | The complaint has been resolved with the necessary evidence. |
| **CLOSED** | The complaint workflow has been completed. |

---

## Technology Stack

| Layer | Technologies |
|---|---|
| **Admin Frontend** | React.js, Vite, Tailwind CSS |
| **Mobile Applications** | React Native, Expo |
| **Backend** | Java, Spring Boot, Spring MVC, Spring Data JPA |
| **Database** | PostgreSQL |
| **Geospatial Database** | PostGIS, Hibernate Spatial |
| **Mapping** | Leaflet, OpenStreetMap |
| **Real-Time Communication** | WebSockets, STOMP, SockJS |
| **GPS / Telematics** | Wialon |
| **Route Processing** | OSRM |
| **Caching** | Redis |
| **Authentication** | JWT, Spring Security |
| **File Storage** | AWS S3 |
| **Containerization** | Docker |
| **Deployment** | AWS EC2, Nginx |
| **CI/CD** | GitHub Actions |
| **Mobile Builds & Updates** | Expo EAS |

---

## Geospatial Technology

SwachhSangli uses geospatial technologies for mapping municipal wards, vehicle locations, complaint locations, and route information.

### PostGIS

PostGIS extends PostgreSQL with geospatial functionality.

It is used for:

- Storing geographic coordinates.
- Managing ward boundaries.
- Spatial queries.
- Geographic location processing.
- Mapping municipal assets and complaints.

### Leaflet & OpenStreetMap

Used for interactive maps to display:

- Live garbage collection vehicles.
- Ward boundaries.
- Complaint locations.
- Vehicle routes.
- Collection points.

### OSRM

Open Source Routing Machine (OSRM) supports road-based routing and map matching.

It helps process GPS coordinates and align vehicle movement with actual road networks, reducing inaccuracies caused by GPS drift and urban signal interference.

---

## Security

The platform implements security mechanisms to protect municipal data and control access.

- JWT-based authentication.
- Spring Security integration.
- Role-Based Access Control (RBAC).
- Protected backend APIs.
- Role-specific authorization.
- Ward-based data access restrictions.
- Secure communication between frontend and backend.
- Controlled access to complaint and operational data.

---

## Deployment Architecture

The platform uses containerized deployment and cloud infrastructure.

```text
                  ┌─────────────────────┐
                  │    GitHub Repo      │
                  └──────────┬──────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │  GitHub Actions     │
                  │   CI/CD Pipeline    │
                  └──────────┬──────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │     AWS EC2         │
                  │                     │
                  │  Docker Containers  │
                  │  Spring Boot API    │
                  │  Nginx             │
                  └──────────┬──────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │   PostgreSQL DB     │
                  │     + PostGIS       │
                  └─────────────────────┘
```

### Deployment Components

- **AWS EC2** – Cloud server for backend services.
- **Docker** – Containerization and application deployment.
- **Nginx** – Reverse proxy and web server.
- **GitHub Actions** – Automated build and deployment workflows.
- **Expo EAS** – Mobile application build and update workflows.

---

## My Contributions

As a full-stack developer contributing to SwachhSangli, I worked on building and integrating different components of the municipal waste management platform.

- Developed full-stack application modules for municipal operations and sanitation management.
- Worked on backend API integration using Spring Boot.
- Developed responsive administrative dashboards using React.js and Tailwind CSS.
- Integrated real-time vehicle tracking data from GPS telematics systems.
- Implemented vehicle monitoring, route visualization, and fleet-related functionalities.
- Worked on geospatial mapping using Leaflet and spatial data technologies.
- Developed complaint management workflows and role-based functionality.
- Integrated real-time updates using WebSocket communication.
- Contributed to database design, application integration, and deployment workflows.

---

## Future Scope

- AI-based garbage collection route optimization.
- Predictive vehicle maintenance.
- Smart waste collection using IoT sensors.
- Automatic waste bin fill-level monitoring.
- Advanced sanitation analytics.
- Automated vehicle performance reports.
- Citizen feedback and service quality analytics.
- AI-powered complaint classification and prioritization.
- Improved collection efficiency using historical operational data.

---

<div align="center">

### Building a Smarter & Cleaner Sangli 🌱

**Technology for cleaner cities, efficient operations, and better citizen services.**

</div>
