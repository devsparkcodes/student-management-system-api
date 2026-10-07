# Student Management System API

A modular REST API built with Python and FastAPI for managing students, course assignments, and validated student information.

## Project Overview

The Student Management System API is a backend application designed to manage student records and course assignments through RESTful endpoints.

The project uses a layered structure with separate routes, services, models, and database components. This organization helps keep the application readable, maintainable, and easier to extend.

## Features

### Student Management

- Create a student
- Get all students
- Get a single student
- Update student information
- Delete a student

### Course Management

- Assign a course to a student
- Get assigned courses
- Update course assignments
- Delete course assignments

### Data Validation

The API uses Pydantic for request and response validation, including:

- Minimum and maximum name length
- Age validation
- Class validation
- Email validation using `EmailStr`
- Nested address validation

### Error Handling

FastAPI's `HTTPException` is used to handle common API errors, including:

- Student not found
- Course not found
- Duplicate course assignment

## How It Works

The application follows a layered architecture:

1. **Routes Layer** — Handles API endpoints and HTTP requests/responses.
2. **Services Layer** — Contains business logic, data processing, and CRUD operations.
3. **Models Layer** — Defines data schemas, validation rules, and request/response structures.
4. **Database Layer** — Uses Python dictionaries as an in-memory database for learning and prototyping.

## Student Model

| Field | Type |
|---|---|
| `student_name` | string |
| `father_name` | string |
| `student_age` | integer |
| `student_current_class` | integer |
| `admission_date` | date |
| `parent_email` | email |
| `address` | object |

### Address Fields

| Field | Type |
|---|---|
| `city` | string |
| `area` | string |
| `house_no` | string |

## Available Courses

| Course No. | Course Name | Duration |
|---:|---|---|
| 1 | Python Basics | 2 months |
| 2 | Python Advanced | 3 months |
| 3 | Front-end Development | 4 months |
| 4 | Back-end Development | 4 months |

## Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| FastAPI | Backend framework |
| Pydantic | Data validation |
| REST API | API architecture |
| Uvicorn | ASGI server |

## Project Structure

```text
TASK-1/
│
├── models/
│   └── student.py
│
├── routes/
│   ├── student.py
│   └── course.py
│
├── services/
│   ├── student_service.py
│   └── course_service.py
│
├── database.py
├── main.py
├── requirements.txt
├── README.md
└── .gitignore
```

## API Documentation

### Student Routes

| Method | Endpoint | Description |
|---|---|---|
| POST | `/students/` | Create student |
| GET | `/students/` | Get all students |
| GET | `/students/{student_id}` | Get a single student |
| PUT | `/students/{student_id}` | Update student |
| DELETE | `/students/{student_id}` | Delete student |

### Course Routes

| Method | Endpoint | Description |
|---|---|---|
| POST | `/courses/{student_id}/{course_no}` | Assign course |
| GET | `/courses/` | Get all assigned courses |
| GET | `/courses/{student_id}` | Get assigned course |
| PUT | `/courses/{student_id}/{course_no}` | Update course |
| DELETE | `/courses/{student_id}` | Delete course |

### Interactive Documentation

After starting the server, FastAPI provides:

- Swagger UI: `http://127.0.0.1:8000/docs`
- ReDoc: `http://127.0.0.1:8000/redoc`

## Getting Started

### 1. Create a Virtual Environment

```bash
python -m venv .venv
```

### 2. Activate the Virtual Environment

**Windows:**

```bash
.venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Development Server

```bash
uvicorn main:app --reload
```

The API will be available at:

```text
http://127.0.0.1:8000
```

## Learning Outcomes

This project helped strengthen practical understanding of:

- FastAPI fundamentals
- REST API development
- CRUD operations
- Pydantic validation
- Dependency Injection
- Layered backend architecture
- Service layer design
- API documentation with Swagger and ReDoc

## Future Improvements

Potential future enhancements include:

- JWT authentication
- SQLite or PostgreSQL integration
- Attendance management
- Marks management
- User roles and permissions
- Automated testing
- Deployment support

## Author

**Muhammad Umar**

Building practical applications at the intersection of software engineering and AI.

- GitHub: https://github.com/devsparkcodes
- LinkedIn: https://linkedin.com/in/devsparkcodes
