# WordPress with MySQL using Docker Compose

This repository provides a basic setup for running WordPress with MySQL using Docker Compose. It is designed to be compatible with both AMD64 and ARM64 architectures.

## Project Structure

```
.
├── docker-compose.yml
├── README.md
└── .gitignore
```

## Services

The setup includes the following services:

- **Database (MariaDB or MySQL)**:
  - By default, this setup uses a MariaDB image (`mariadb:10.6.4-focal`) to ensure compatibility across different architectures.
  - If you prefer to use MySQL, uncomment the following line in `docker-compose.yml`:
    ```yaml
    image: mysql:8.0.27
    ```
- **WordPress**:
  - Uses the latest WordPress image (`wordpress:latest`).
  - Exposes port `80` to map to port `80` of the host machine.
  - Automatically restarts using `restart: always`.

## Deployment

To deploy the WordPress application, run the following command:

```sh
docker compose up -d
```

This will:
- Create a Docker network named `wordpress-mysql_default`.
- Create a volume `wordpress-mysql_db_data` for database persistence.
- Start the WordPress and database containers.

## Compatibility Notes

🔹 For cross-platform compatibility:
- **MariaDB is used by default** to support both AMD64 and ARM64.
- You can switch to MySQL by uncommenting the `mysql` image line in `docker-compose.yml`.

## References

For more details, visit the official WordPress Docker page:
[WordPress Docker Official Documentation](https://hub.docker.com/_/wordpress)

## License

This project is licensed under the MIT License.

