# Turf-Booking-and-Management-System

The application provides a seamless interface for users to view turf availability, book slots, make payments, and manage their bookings, while giving turf owners tools to manage the facility, track bookings, analyze trends, and optimize operations.

## Table of Contents

- [Problem Statement](#problem-statement)
- [Demo Video](#demo-video)
- [Tech Stack Used](#tech-stack-used)
- [Single Turf Focus: The SK Sports Turf](#single-turf-focus-the-sk-sports-turf)
- [How to Run the Application](#how-to-run-the-application)
- [Important Configuration](#important-configuration)
- [Main Routes](#main-routes)

## Problem Statement

With less availability of open grounds, turf has emerged as a practical way for people to play together at reasonable rates. Booking turf manually is difficult for users who need to locate facilities, check availability, and book suitable timings. This project solves that by allowing users to check slot availability, select timings, book instantly, and view booking history.

## Demo Video

[Click here to watch the demo video](https://github.com/mallu201/Turf-Booking-and-Management-System/raw/main/video.mp4)

## Tech Stack Used

### Front-End

- HTML
- CSS
- JavaScript
- Bootstrap

### Back-End

- Python (Django)
- SQLite (default in current setup)
- MySQL (dependency support available)

## Single Turf Focus: The SK Sports Turf

The project is focused on one facility: **The SK Sports Turf**.

### Key Features

- Single turf branding and dedicated booking flow.
- Time-slot booking with validation to prevent double booking.
- User authentication and booking history.
- Owner dashboard with:
  - Daily, weekly, monthly, and yearly income reports
  - Booking management
  - Payment tracking
  - Turf settings management
- Slot price management from settings/admin.

### Technical Improvements

- Slot unavailability checks to prevent duplicate bookings.
- Dynamic pricing through turf settings.
- Analytics charts and reports for owner insights.
- Responsive UI with Bootstrap.

## How to Run the Application

### 1) Install Python

- Install Python **3.13.x** (runtime file contains `Python 3.13.7`).
- Enable **Add Python to PATH** during install.

Verify:

```bash
python --version
pip --version
```

### 2) Open project folder

```bash
cd SKSportsPark
```

### 3) Create virtual environment

```bash
python -m venv .venv
```

### 4) Activate virtual environment

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

Windows CMD:

```cmd
.venv\Scripts\activate.bat
```

Linux/macOS:

```bash
source .venv/bin/activate
```

### 5) Install packages

```bash
pip install --upgrade pip setuptools wheel
pip install -r requirements.txt
```

### 6) Apply migrations

```bash
python manage.py migrate
```

### 7) Create users

Create admin user:

```bash
python manage.py createsuperuser
```

Create owner/staff user:

```bash
python manage.py create_owner
```

Optional non-interactive owner creation:

```bash
python manage.py create_owner --username owner --email owner@example.com --password "StrongPass123!" --noinput
```

### 8) Run server

```bash
python manage.py runserver
```

Open:

- App: `http://127.0.0.1:8000/`
- Admin: `http://127.0.0.1:8000/admin/`
- Owner login: `http://127.0.0.1:8000/owner/login/`

## Important Configuration

File: `SKSportsPark/settings.py`

- `OFFLINE_MODE = True`
- `ENABLE_EMAIL = False`
- Database uses SQLite fallback or `DATABASE_URL` when provided.

## Main Routes

- `/` home
- `/book_now/` booking
- `/turf_details/`
- `/slot_details/`
- `/turfBilling/`
- `/success/`
- `/login/`, `/signup/`, `/logout/`
- `/orderHistory/`, `/allBookings/`
- `/owner/login/`, `/owner/dashboard/`, `/owner/bookings/`, `/owner/payments/`, `/owner/settings/`, `/owner/analytics/`
- `/check_slot_status/`, `/check_username/`, `/check_email/`

