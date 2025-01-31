# ALX Travel App

A Django REST API for managing property listings and bookings. This application provides endpoints for creating and managing property listings, handling bookings, and managing reviews.


## Features

- Property Listings Management
- Booking System
- Review System
- User Authentication
- API Documentation with Swagger/ReDoc
- MySQL Database Integration
- Celery Task Queue Integration
- Database Seeding for Development

## Tech Stack

- Python 3.x
- Django 4.x
- Django REST Framework
- MySQL
- Redis (for Celery)
- Swagger/ReDoc for API documentation

## Prerequisites

- Python 3.x
- MySQL
- Redis
- Docker (optional)

## Setup

1. Clone the repository:
```bash
git clone <repository-url>
cd alx_travel_app
```

2. Create a virtual environment and activate it:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Set up MySQL database:
```bash
# Using Docker
docker run --name alx_travel_mysql \
    -e MYSQL_ROOT_PASSWORD=rootpassword \
    -e MYSQL_DATABASE=alx_travel_db \
    -e MYSQL_USER=alx_travel_user \
    -e MYSQL_PASSWORD=alx_travel_pass \
    -p 3306:3306 -d mysql:latest
```

5. Create a `.env` file in the project root (use `.env.example` as a template):
```bash
cp .env.example .env
# Edit .env with your configuration
```

6. Run migrations:
```bash
python manage.py migrate
```

7. Create a superuser:
```bash
python manage.py createsuperuser
```

8. (Optional) Seed the database with sample data:
```bash
python manage.py seed
```
This will create:
- 7 sample users (5 regular users, 2 staff users)
- 14 property listings (2 per user)
- Multiple bookings and reviews
All sample users have the password: `password123`

## Running the Application

1. Start the development server:
```bash
python manage.py runserver
```

2. Start Celery worker (in a separate terminal):
```bash
celery -A alx_travel_app worker -l info
```

## API Endpoints

The API provides the following endpoints:

- `/api/listings/` - Property listings management
- `/api/bookings/` - Booking management
- `/api/reviews/` - Review management
- `/swagger/` - Swagger API documentation
- `/redoc/` - ReDoc API documentation
- `/admin/` - Admin interface
- `/api-auth/` - Authentication endpoints

## Authentication

The API uses Django REST Framework's built-in authentication. To access protected endpoints:

1. Create a user account or use the superuser account
2. Use the login endpoint or session authentication
3. Include authentication credentials in your requests

## API Documentation
The API is fully documented using Swagger/OpenAPI specification. You can explore and test the API endpoints using the interactive documentation.

### Swagger UI
![Swagger UI](assets/swagger.png)
- Swagger UI: `/swagger/`
- ReDoc: `/redoc/`

## Development

1. Make sure to create and activate a virtual environment
2. Install development dependencies
3. Follow PEP 8 style guide
4. Write tests for new features
5. Update documentation as needed


## Testing

Run the test suite:
```bash
python manage.py test
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.
