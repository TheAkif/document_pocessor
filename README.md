# Document Processor

This is a simple Django project that demonstrates how to Dockerize a Django application and connect it to a PostgreSQL database using Docker Compose. It also includes a setup for Django Rest Framework to create APIs.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

Make sure you have the following installed on your system:

- Docker
- Docker Compose
- VS Code. (Optional)

### Installing

1. Clone the repository to your local machine: 
```bash 
git clone https://github.com/TheAkif/document_pocessor.git
```
2. Navigate to the project directory.
```bash
cd document_processor
```
3. Start the Docker containers: 
```bash
docker-compose up -d --build
```
4. Open another terminal go to the project directory and create a superuser for the Django application:
```bash
docker-compose exec web python manage.py createsuperuser
```

5. Access the Django admin interface:

Open a web browser and go to http://localhost:8000/admin. Log in using the superuser credentials you just created.

6. Verify that you can see the superuser created in the database:
```bash
docker-compose exec db psql -U postgres
```

7. Once you're connected to the database, run the following commands to see the `auth_user` table:
```bash
\c postgres
SELECT * FROM auth_user;
```

## 💅 Code Formatters
**Backend:**
[Black](https://github.com/psf/black) is used for backend code formatter.
```bash
./black.sh
```

### Running backend tests

```bash
python3 manage.py test --keepdb
```

For running specific unit test case use tag name ie.
```bash
python3 manage.py test --keepdb --tag=<tag-name>

```
