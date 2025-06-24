# Redis Stack with Docker Compose

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
- Ensure the password includes a mix of upper/lowercase letters.
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

## 📦 Accessing Redis

After the container is running, you can connect using a Redis client like `redis-cli`:

```bash
redis-cli -h localhost/ip -p 6379 -a your_password_here
```

Replace `your_password_here` with the same password used in the `compose.yml` file.

---

## 📚 References

- [Redis Stack Documentation](https://redis.io/docs/stack/)
- [Docker Hub: redis/redis-stack-server](https://hub.docker.com/r/redis/redis-stack-server)