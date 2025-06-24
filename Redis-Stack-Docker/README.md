<<<<<<< HEAD
# ![Redis Logo](https://redis.io/images/redis-white.png) Redis Stack with Docker Compose
=======
# Redis Stack with Docker Compose
>>>>>>> 732c5af7d2a49606868f6cf582ba8655b6194a8c

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
<<<<<<< HEAD
- Ensure the password includes a mix of upper/lowercase letters, numbers, and special characters.
=======
- Ensure the password includes a mix of upper/lowercase letters.
>>>>>>> 732c5af7d2a49606868f6cf582ba8655b6194a8c
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

<<<<<<< HEAD
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
=======

>>>>>>> 732c5af7d2a49606868f6cf582ba8655b6194a8c

---

## 📦 Accessing Redis

<<<<<<< HEAD
### Using redis-cli:
```bash
redis-cli -h localhost -p 6379 -a your_password_here
```

Replace `your_password_here` with the same password used in the `docker-compose.yml` file.

### Using RedisInsight (Web UI):
Once the container is running, you can access **RedisInsight** in your browser:
=======
After the container is running, you can connect using a Redis client like `redis-cli`:

```bash
redis-cli -h localhost/ip -p 6379 -a your_password_here
```

Replace `your_password_here` with the same password used in the `compose.yml` file.
>>>>>>> 732c5af7d2a49606868f6cf582ba8655b6194a8c

---

## 📚 References

- [Redis Stack Documentation](https://redis.io/docs/stack/)
<<<<<<< HEAD
- [Docker Hub: redis/redis-stack-server](https://hub.docker.com/r/redis/redis-stack-server)
- [RedisInsight](https://redis.io/docs/ui/insight/)
=======
- [Docker Hub: redis/redis-stack-server](https://hub.docker.com/r/redis/redis-stack-server)
>>>>>>> 732c5af7d2a49606868f6cf582ba8655b6194a8c
