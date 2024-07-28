### README for Drupal Docker Setup

# Drupal Docker Setup

This repository provides a comprehensive Drupal environment using Docker Compose. It includes configurations for MySQL, PHP, and Nginx containers. An `.env` file is included for managing MySQL passwords securely, ensuring a streamlined and secure setup process for developers. Ideal for anyone looking to get started with Drupal development using Docker.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Setup Instructions](#setup-instructions)
- [Running the Project](#running-the-project)
- [Adjustments](#adjustments)
- [License](#license)

## Prerequisites

Ensure you have the following installed on your machine:

- Docker
- Docker Compose

## Setup Instructions

1. **Clone the Repository**

   ```bash
   git clone https://github.com/Dhruvranaji/docker-drupal-setup.git
   cd docker-drupal-setup
   ```

2. **Rename `.env` File**

   Rename the `example.env` file to `.env` and adjust the MySQL credentials as needed:

   ```bash
   mv example.env .env
   ```

3. **Install Drupal**

   If you want to install the latest version of Drupal, use the following Composer command:

   ```bash
   composer create-project drupal/recommended-project .
   ```

   If you want to use an existing setup, ensure your Drupal files are in the project directory.

4. **Adjust PHP Container Image**

   Adjust the PHP container image as per the required Drupal version. In this example, we are using PHP 8.2.

5. **Run Docker Compose**

   Start the Docker containers using the following command:

   ```bash
   docker compose up -d --build
   ```

## Running the Project

- Access your Drupal site at: `http://localhost:8091`
- Adjust the port in the `docker-compose.yml` and `nginx.conf` file if you need to use a different port.

## Adjustments

- **Nginx Port**: By default, Nginx is set to use port 8091. You can change this in the `docker-compose.yml` and `nginx.conf` file.
- **PHP Version**: Ensure the PHP version in the Dockerfile matches the requirements of your Drupal version.
- **Database Configuration**: Modify the `.env` file to set your database credentials.

## License

This project is licensed under the MIT License. See the [(LICENSE)](https://github.com/Dhruvranaji/docker-drupal-setup/blob/main/LICENSE) file for details.

## Contribution Guidelines

Thank you for your interest in this project. At this time, we are not accepting direct contributions or pull requests. However, you are welcome to fork this repository and make changes to your own copy.

If you have any questions or need assistance, please feel free to open an issue.
