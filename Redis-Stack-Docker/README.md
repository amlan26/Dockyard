# ![Redis Logo](https://redis.io/images/redis-white.png) Redis Stack with Docker Compose

This repository provides a minimal and secure setup to run [Redis Stack](https://hub.docker.com/r/redis/redis-stack-server) using Docker Compose.

## 🚀 Features

- Uses the official `redis/redis-stack-server:latest` image from Docker Hub
- Exposes Redis on port `6379`
- Data persistence with Docker volumes
- Secure setup using `--requirepass`
- Auto-restart enabled on failure or reboot

---

## 🔐 Security Note

- **Password Requirement**: Redis Stack **will not start** unless a strong password is set using `--requirepass`.
- Ensure the password includes a mix of upper/lowercase letters, numbers, and special characters.
- Redis does not use a username; authentication is handled with the password only.

---

## 🐳 Docker Compose Setup

### 1. Start Redis Stack
```bash
docker compose up -d
```

### 2. Stop and Remove All Containers
```bash
docker compose down
```

---

## 🧩 Docker Compose File

Below is the included `docker-compose.yml`:

```yaml
services:
  redis_stack:
    image: redis/redis-stack-server:latest
    container_name: redis-stack
    command: redis-stack-server --requirepass 12345  # Use a strong password!
    ports:
      - 6379:6379
    volumes:
      - redis_data:/data
    restart: always

volumes:
  redis_data:
```

---

## 📦 Accessing Redis

### Using redis-cli:
```bash
redis-cli -h localhost -p 6379 -a your_password_here
```

Replace `your_password_here` with the same password used in the `docker-compose.yml` file.

### Using RedisInsight (Web UI):
Once the container is running, you can access **RedisInsight** in your browser:

---

## 📚 References

- [Redis Stack Documentation](https://redis.io/docs/stack/)
- [Docker Hub: redis/redis-stack-server](https://hub.docker.com/r/redis/redis-stack-server)
- [RedisInsight](https://redis.io/docs/ui/insight/)