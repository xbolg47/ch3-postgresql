# Django + PostgreSQL Project

This project is a Django web application configured to run with a PostgreSQL database using Docker. It provides a robust development environment for building and testing Django applications with a production-grade database backend.

## Features
- Django 4.0.10
- PostgreSQL 13
- Dockerized setup for easy development and deployment

## Prerequisites
- [Docker](https://www.docker.com/get-started) and [Docker Compose](https://docs.docker.com/compose/) installed on your machine

## Getting Started

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd ch3-postgresql
   ```

2. **Build and start the services:**
   ```bash
   docker-compose up --build
   ```
   This will start both the Django development server and the PostgreSQL database.

3. **Access the application:**
   Open your browser and go to [http://localhost:8000](http://localhost:8000)

## Project Structure
- `docker-compose.yml`: Defines the Docker services (web and db)
- `Dockerfile`: Builds the Django application image
- `requirements.txt`: Python dependencies
- `manage.py`: Django management script
- `django_project/`: Django project source code (your main app may be inside this directory)

## Database
- The PostgreSQL database data is stored in a Docker volume (`postgres_data`) to persist data between container restarts.
- Default authentication is set to trust for development convenience.

## Running Management Commands
You can run Django management commands inside the running web container. For example:
```bash
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
```

## Stopping the Application
To stop the application, press `Ctrl+C` in the terminal where Docker Compose is running, then run:
```bash
docker-compose down
```

## License
Specify your project's license here.

---
Feel free to customize this README with more details about your specific Django apps, environment variables, or deployment instructions as needed.
