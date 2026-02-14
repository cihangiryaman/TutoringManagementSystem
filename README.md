# Tutoring Management System

<p align="center">
  <strong>A comprehensive multi-tenant SaaS platform for private tutors to manage students, lessons, payments, and schedules.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/.NET-8.0-512BD4?style=flat&logo=dotnet" alt=".NET 8.0" />
  <img src="https://img.shields.io/badge/ASP.NET%20Core-MVC-512BD4?style=flat&logo=dotnet" alt="ASP.NET Core MVC" />
  <img src="https://img.shields.io/badge/SQL%20Server-Database-CC2927?style=flat&logo=microsoftsqlserver" alt="SQL Server" />
  <img src="https://img.shields.io/badge/Docker-Containerized-2496ED?style=flat&logo=docker" alt="Docker" />
</p>

---

## Overview

**Tutoring Management System** is a modern web application designed for private tutors and educational institutions to efficiently manage their tutoring business. The platform provides a user-friendly interface for tracking students, scheduling lessons, monitoring payments, and analyzing earnings.

Built with Clean Architecture principles and multi-tenant support, Cadap allows multiple tutors to use the same platform with complete data isolation.

Actively using by 5 teachers and 50+ students

https://www.ozelderstakipsistemi.com

---

## ScreenShots
### Desktop
<img src="images/Home-Screen.png" alt="alt text" width="49.5%"> <img src="images/Calendar-View.png" alt="alt text" width="49.5%">
<img src="images/Student-Detail.png" alt="alt text" width="49.5%"> <img src="images/Earnings.png" alt="alt text" width="49.5%">

### Mobile
<img src="images/Home-Screen-m.png" alt="alt text" width="24.3%"> <img src="images/Calendar-View-m.png" alt="alt text" width="24.3%"> <img src="images/Student-Detail-m.png" alt="alt text" width="24.3%"> <img src="images/Earnings-m.png" alt="alt text" width="24.3%">
---

## Features

### Core Features
- **Student Management** - Create and manage student profiles with detailed information including contact details, grade level, and school information
- **Lesson Scheduling** - Schedule, track, and manage individual tutoring sessions with date, duration, and pricing
- **Payment Tracking** - Monitor paid and unpaid lessons, track earnings over time
- **Earnings Dashboard** - Visualize income with detailed reports and analytics
- **Calendar View** - Interactive calendar to view past and upcoming lessons

### Platform Features
- **Multi-Tenancy** - Each tutor gets their own isolated workspace with custom URL slug
- **Authentication & Authorization** - Secure login with ASP.NET Core Identity
- **Responsive Design** - Works seamlessly on desktop and mobile devices
- **Excel Export** - Export data to Excel using EPPlus
- **Comprehensive Logging** - Structured logging with Serilog
- **RESTful API** - Swagger/OpenAPI documentation for API endpoints

I used Multi-Tenancy to enable the project to scale for institutional use.

---

## Architecture

TMS follows **Clean Architecture** principles with clear separation of concerns:


![Architectural Overview](images/Architectural-Overview.png)


### Request Flow

![Request-Flow](images/Request-Flow.png)

---

## Tech Stack

| Category | Technology |
|----------|------------|
| **Framework** | .NET 8.0, ASP.NET Core MVC |
| **Database** | SQL Server with Entity Framework Core 8.x |
| **Authentication** | ASP.NET Core Identity |
| **Object Mapping** | AutoMapper |
| **Logging** | Serilog (Console, File sinks) |
| **API Documentation** | Swashbuckle/Swagger |
| **Excel Export** | EPPlus |
| **Containerization** | Docker |
| **Frontend** | Razor Views, HTML5, CSS3, JavaScript |

---

## 📁 Project Structure

```
TMS/
├── TMS.sln                    # Solution file
├── Dockerfile                   # Docker build configuration
├── README.md                    # This file
│
├── TMS.Domain/                # Domain Layer
│   ├── Models/                  # Entity models (Student, Lesson, Tenant, etc.)
│   ├── Interfaces/              # Repository interfaces
│   ├── Contracts/               # Domain contracts (IMustHaveTenant, etc.)
│   └── Common/                  # Base entities and common types
│
├── TMS.Application/           # Application Layer
│   ├── Services/                # Business logic services
│   ├── DTO/                     # Data Transfer Objects
│   ├── Interfaces/              # Service interfaces
│   ├── Profiles/                # AutoMapper profiles
│   ├── Validators/              # Input validation
│   └── DependencyContainer.cs   # DI registration
│
├── TMS.Infrastructure/        # Infrastructure Layer
│   ├── Contexts/                # EF Core DbContext
│   ├── Repositories/            # Repository implementations
│   ├── Migrations/              # Database migrations
│   ├── CustomIdentity/          # Custom Identity managers
│   ├── Configurations/          # Entity configurations
│   ├── Settings/                # App settings models
│   ├── Store/                   # Tenant store
│   └── Routing/                 # Custom route constraints
│
├── TMS.UI.Web/                # Web Presentation Layer
│   ├── Controllers/             # MVC Controllers
│   ├── Views/                   # Razor Views
│   ├── Models/                  # View Models
│   ├── Middleware/              # Custom middleware (Tenant, etc.)
│   ├── StartupExtensions/       # Service registration extensions
│   ├── wwwroot/                 # Static files (CSS, JS, images)
│   └── Program.cs               # Application entry point
│
├── TMS.UI.WinForms/           # Windows Forms client (optional)
│
└── TMS.Shared/                # Shared utilities and caching
    └── Cache/                   # Caching utilities
```

---

## Multi-Tenancy

TMS supports multi-tenancy with URL-based tenant identification:

```
https://ozelderstakipsistemi.com/{tenant-slug}/Home
https://ozelderstakipsistemi.com/{tenant-slug}/Students
https://ozelderstakipsistemi.com/{tenant-slug}/Lessons 
etc.
```

Each tenant has:
- **Isolated data** - Complete data separation
- **Custom slug** - Unique URL identifier
- **Independent settings** - Per-tenant configuration

---

## 📬 Contact

The project is a close-source but I can give you the source code if you ask me!

[![LinkedIn](https://custom-icon-badges.demolab.com/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin-white&logoColor=fff)](https://www.linkedin.com/in/cihangir-yaman/) 

---

<p align="center">
  <em>Built with ❤️ for educators and tutors worldwide</em>
</p>
