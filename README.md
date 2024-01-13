# Laravel Dockerized Project

## Introduction

This project is a Dockerized setup for a Laravel application using Docker Compose. Follow the steps below to get started.

## Prerequisites

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Installation

1. Clone this repository to your local machine:

    ```bash
    git clone git@github.com:Murasso2/Laravel_template.git your-project
    cd your-project
    ```

2. Run the following command to start the Docker containers:

    ```bash
    docker-compose up -d
    ```

3. Build the Laravel application:

    ```bash
    docker-compose build app
    ```

4. Access the MySQL database using the following command:

    ```bash
    docker-compose exec db mysql -u root -p
    ```

   - Enter the password when prompted. (By default, it's set to `rootpassword`)

5. Inside the Laravel application container, create a new Laravel project:

    ```bash
    docker-compose exec app composer create-project laravel/laravel .
    ```

6. Rebuild the Docker image for the Laravel application:

    ```bash
    docker-compose build app
    ```

7. Adjust ownership of project files:

    ```bash
    sudo chown -R $USER:$USER .
    ```

8. Run Laravel migrations:

    ```bash
    docker-compose exec app php artisan migrate
    ```

## Usage

Now that the project is set up, you can access your Laravel application at [http://localhost](http://localhost). Make sure your Docker containers are running:

```bash
docker-compose ps
