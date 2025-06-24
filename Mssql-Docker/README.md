# 🛢️ SQL Server Docker Setup

This project provides a Docker-based setup to run Microsoft SQL Server 2022 using Docker Compose. It uses a named volume for persistent storage.

## 📦 Service Details

### `sql-server`

- **Image**: `mcr.microsoft.com/mssql/server:2022-latest`
- **Container Name**: `sql-server`
- **Ports**: `1433:1433`
- **Environment Variables**:
  - `ACCEPT_EULA=Y` – Accepts the Microsoft SQL Server license agreement.
  - `MSSQL_SA_PASSWORD=abcd@123` – **Strong password required** (at least 8 characters, including uppercase, lowercase, number, and special character).
  - `TZ=Asia/Dhaka` – Sets container timezone.
- **Username**: Default SQL Server username is `sa`
- **Volume**:
  - `sql-data:/var/opt/mssql` – Persists SQL Server data across container restarts.

> 📌 **Note**: The `MSSQL_SA_PASSWORD` must be strong. The container will not start if the password policy is not met.

## 📁 Directory Structure

```
.
├── compose.yml
└── README.md
```

## 🚀 Getting Started

### 1. Start SQL Server

```bash
docker compose up -d
```

### 2. Stop and Remove the Container

```bash
docker compose down
```

### 3. Remove Container and Volume

```bash
docker compose down -v
```

## 🐳 Customize Image Version

You can use a different SQL Server version from [Docker Hub](https://hub.docker.com/_/microsoft-mssql-server) by updating the `image` line in `docker-compose.yml`, for example:

```yaml
image: mcr.microsoft.com/mssql/server:2019-latest
```

## 🔗 Connect to SQL Server

You can connect using:

- **SQL Server Management Studio (SSMS)**
- **Azure Data Studio**
- **Command Line Tools**:
  ```bash
  docker exec -it sql-server /opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P 'abcd@123'
  ```
