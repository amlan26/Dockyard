# MongoDB Docker Setup

This project provides a Docker-based setup to run a MongoDB Community Server using Docker Compose. It uses a named volume for persistent data storage and a custom network for isolation.

## 📦 Services

### `mongodb`

- **Image**: `mongodb/mongodb-community-server:latest`
- **Ports**: `27017:27017`
- **Environment Variables**:
  - `MONGO_INITDB_ROOT_USERNAME`: `mongo`
  - `MONGO_INITDB_ROOT_PASSWORD`: `12345`
- **Volumes**:
  - `mongodb_data:/data/db`
- **Network**:
  - `mongo_network`

## 📁 Directory Structure

```
.
├── compose.yml
└── README.md
```

## 🚀 Getting Started

### 1. Run MongoDB container

```bash
docker compose up -d
```

This will start MongoDB in detached mode.

### 2. Verify the container

```bash
docker ps -a
```

You should see `mongodb` running.

### 3. Connect to MongoDB

Use any MongoDB client (e.g. [MongoDB Compass](https://www.mongodb.com/products/compass)) or CLI:

```bash
mongo -u mongo -p 12345 --authenticationDatabase admin
```

Or via Docker:

```bash
docker exec -it mongodb mongosh -u mongo -p 12345 --authenticationDatabase admin
```

## 🧹 Stopping & Cleaning Up

To stop the container:

```bash
docker compose down
```

To remove volumes as well:

```bash
docker compose down -v
```