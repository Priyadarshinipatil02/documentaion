# Backend Setup Using Docker Compose

This documentation outlines the steps and configurations required to set up a backend development environment with Docker Compose. The environment includes a Java-based backend, a PostgreSQL database, and a pgAdmin instance for managing the database. The database is also pre-seeded with initial data for seamless development.

---

## 1. Storing Sensitive Data in `.env` File

### Purpose
To ensure sensitive information (e.g., database credentials, API keys) is not exposed or pushed to version control.

### Steps
1. Create a `.env` file in the root directory of your project.
2. Add the sensitive data as environment variables. For example:
   ```dotenv
   DB_USERNAME=your_username
   DB_PASSWORD=your_password
   DB_NAME=your_dbname
 
 3. Add the .env file to. gitignore to prevent it from being committed:

## 2. Creating a docker-compose.yml File

The docker-compose.yml file defines all backend services, including the Java backend, PostgreSQL database, and pgAdmin.

### Key Points:
1.	The backend service is built from the Dockerfile located in the root directory.
2.	The PostgreSQL service uses a db_seed folder for initializing the database with seed data.
3.	pgAdmin provides a web-based interface for database management.


### Sample `docker-compose.yml` File

```yaml
version: "3.8"
services:
  backend:
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "8080:8080"
    environment:
      - DB_HOST=db
      - DB_PORT=5432
      - DB_NAME=${DB_NAME}
      - DB_USERNAME=${DB_USERNAME}
      - DB_PASSWORD=${DB_PASSWORD}
    depends_on:
      - db

  db:
    image: postgres:latest
    container_name: postgres_db
    ports:
      - "5432:5432"
    environment:
      POSTGRES_USER: ${DB_USERNAME}
      POSTGRES_PASSWORD: ${DB_PASSWORD}
      POSTGRES_DB: ${DB_NAME}
    volumes:
      - ./db_seed:/docker-entrypoint-initdb.d

  pgadmin:
    image: dpage/pgadmin4
    container_name: pgadmin
    ports:
      - "80:80"
    environment:
      PGADMIN_DEFAULT_EMAIL: ${PGADMIN_EMAIL}
      PGADMIN_DEFAULT_PASSWORD: ${PGADMIN_PASSWORD}
```

### 3. Starting All Backend Services Locally
 
 1.	Ensure Docker is installed and running on your machine.
2.	Run the following command in the root directory of the project:
3.	Docker-compose up --build
4.	This will:
- `Build the backend application`
- `Start the PostgreSQL database`
- `Launch pgAdmin for database management`

5.	Access the services:
- `Backend: http://localhost:8080`
- `pgAdmin: http://localhost`
- `Login with`	
- `Email: {Email}`	
- `Password: {Password}`		

6.	Connecting pgAdmin to the Database:
- `Add a new server in pgAdmin`
1.	Name: {Your dbname}
2.	Host: db
3.	Port: 5432
4.	Username: {Your Username}
5.	Password: {Your Password}

With this setup: All backend services can be started with a single docker compose up command. Sensitive data is managed securely via an .env file.The database is pre-loaded with initial data, allowing frontend developers to begin their work without delay. pgAdmin is included to manage and inspect the database visually.


