# Django Project Docker Setup
This repository contains a Dockerized setup for a Django application with a PostgreSQL database. It includes a docker-compose.yml file for managing services, a Dockerfile for building the Django application image, and a requirements.txt for dependencies.

## 📋 Features
* **Automated Database Migrations:** Migrations are applied automatically each time the container starts, ensuring your database schema is always up-to-date.
* **Pre-configured PostgreSQL Database:** Environment variables allow for easy customization of database settings.
* **Flexible Volume and Port Mapping:** Volumes persist data, and ports are configurable for host access.

## 🔧 Configuration Overview
You can modify the following settings in docker-compose.yml:

**Environment Variables:**
* POSTGRES_NAME: Database name (default: my_database).
* POSTGRES_USER: Database username (default: admin).
* POSTGRES_PASSWORD: Database password (default: admin).
Ports:
* Django server: 8000 (default, customizable)
* PostgreSQL: 5432 (default, customizable)

# 🚀 Getting Started
1. **Build and Start Services**
  Run the following command to build and launch the containers. This will start the Django server on http://localhost:8000 and apply all migrations.
   ```bash
   docker-compose up --build
2. 1. **Install Additional Dependencies**
Add any required dependencies to requirements.txt, and they will be installed during the build process.

# 🛠 Database Customization
To customize the exposed Django server port, update docker-compose.yml:
   ```bash
   environment:
      - POSTGRES_NAME=my_custom_database
      - POSTGRES_USER=my_user
      - POSTGRES_PASSWORD=my_password
    ports:
      - "8080:8000"
   ```
# 🧑‍💻	Django Configuration
Update the seetins.py file

   ```bash
      DATABASES = {
          "default": {
              "ENGINE": "django.db.backends.postgresql",
              'NAME': 'my_database',
              'USER': 'admin',
              'PASSWORD': 'admin',
              'HOST': 'db',
              'PORT': '5432',
          }
      }
   ```
