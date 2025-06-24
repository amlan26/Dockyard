# 🐘 PostgreSQL with Docker Compose

This repository provides a simple Docker Compose setup to run PostgreSQL in a containerized environment.

---

## 📦 Included Components

- **PostgreSQL 16.3** container
- **Persistent storage** mapped to a local directory
- **Customizable environment variables**

---

## 🚀 Getting Started

### 1. 🔧 Customize Your Configuration (Optional)

Before you run the container, you can customize the following in the `docker-compose.yml` file:

- `POSTGRES_USER`: Change to your preferred PostgreSQL username
- `POSTGRES_PASSWORD`: Set a secure password
- `POSTGRES_DB`: Change the default database name
- `image`: Change the PostgreSQL version (e.g., `postgres:15`, `postgres:14`)
- `device`: Change the host directory path for data persistence (e.g., `./my-backup-folder`)

### 2. ▶️ Start the PostgreSQL Container

Run the following command to start the container in detached mode:

```bash
docker compose up -d
```

This will:
- Download the `postgres:16.3` image if not already present
- Create a container named `db`
- Mount `./db-data` as the persistent storage
- Expose PostgreSQL on port `5432`

### 3. 🛑 Stopping and Removing the Container

To stop and remove the container and associated network:

```bash
docker compose down
```

> 🔒 Your database data will remain safe in the `./db-data` folder unless you manually delete it.

---

## 📁 Folder Structure

```text
.
├── docker-compose.yml
└── db-data/          # PostgreSQL data persisted here
```

---

## 📝 Notes

- Make sure port `5432` is free on your host machine.
- The data volume is bound to your local machine for easy backup and restore.
- Suitable for local development and testing.

---

## 📚 References

- [PostgreSQL Official Docker Image](https://hub.docker.com/_/postgres)
- [Docker Compose Documentation](https://docs.docker.com/compose/)

---

Happy Developing! 🐳