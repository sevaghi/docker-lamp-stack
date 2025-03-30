
# Docker LAMP Stack Project

This project sets up a LAMP (Linux, Apache, MySQL, PHP) stack using Docker and Docker Compose. The goal is to create a simple environment for local development, with separate containers for the Apache web server, MySQL database, and PHP.

## Project Structure

- **`Dockerfile`**: Configuration for the Apache + PHP container.
- **`docker-compose.yml`**: Defines the services, networks, and volumes in Docker Compose.
- **`src/`**: Contains the PHP application files.
- **`.env`**: Environment configuration file (database credentials, etc.).
- **`.gitignore`**: To exclude sensitive files like `.env` from version control.

## Requirements

- [Docker](https://www.docker.com/get-started) installed on your machine.
- [Docker Compose](https://docs.docker.com/compose/install/) to manage the services.

## Setup

1. **Clone the repository** to your local machine:

   ```bash
   git clone https://github.com/sevaghi/docker-lamp-stack.git
   cd docker-lamp-stack
   ```

2. **Configure environment variables** in the `.env` file. Make sure to define the MySQL credentials:

   ```env
   MYSQL_ROOT_PASSWORD=rootpassword
   MYSQL_USER=user
   MYSQL_PASSWORD=userpassword
   MYSQL_DATABASE=mydatabase
   ```

3. **Build and run the containers**:

   Use the following command to build the images and start the Docker containers:

   ```bash
   docker-compose up --build -d
   ```

4. **Access the application**:

   Open your browser and go to [http://localhost:8080](http://localhost:8080). You should see the output of the `phpinfo()` function, indicating that Apache and PHP are working correctly.

5. **Access phpMyAdmin** (optional):

   If you have included phpMyAdmin in the `docker-compose.yml` configuration, you can access it at [http://localhost:8081](http://localhost:8081) to manage your MySQL database.

## Important Files

- **`docker-compose.yml`**: Defines the containers, networks, and volumes for Apache, MySQL, and phpMyAdmin (if included).
- **`Dockerfile`**: Defines how the Apache + PHP image is built.
- **`src/`**: Contains the PHP application files. It's mounted as a volume for easy development.
- **`.env`**: Contains database credentials and other configurable parameters.

## Security

Make sure not to push the `.env` file to GitHub as it contains sensitive credentials. You can use `.gitignore` to exclude it from version control.

## Additional Information

This project is intended for local development and testing purposes. If you plan to deploy it in a production environment, additional security measures and optimizations should be applied.
