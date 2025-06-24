# 🐳 Docker Installation Guide for Linux

This guide provides step-by-step instructions to install Docker on a Linux system using the official Docker installation script.

---

## 🛠 Prerequisites

- A Linux distribution (e.g., Ubuntu, Debian, CentOS, or Fedora)
- Sudo privileges or root access
- Stable internet connection

---

## 📦 Installation Steps

### 1. Download the Docker Installation Script

```bash
sudo curl -fsSL https://get.docker.com -o get-docker.sh
```

### 2. Execute the Installation Script

```bash
sudo sh get-docker.sh
```

### 3. Verify Installation

Check the Docker version to confirm successful installation:

```bash
docker --version
```

**Expected output (example):**

```
Docker version 27.3.1, build ce12230
```

---

## ⚙️ Post-Installation (Optional)

To run Docker commands without `sudo`, add your user to the `docker` group:

```bash
sudo usermod -aG docker $USER
```

Then apply the group changes by either:

```bash
newgrp docker
```

Or log out and back in.

---

## 📚 Reference

For more details, visit the official Docker documentation:  
👉 https://docs.docker.com/engine/install/

---

## 📝 Additional Notes

- This guide is **specific to Linux systems only**.
- Make sure your system is up to date before installation:

```bash
sudo apt update && sudo apt upgrade
```

- The script will automatically detect your Linux distribution and install the appropriate Docker version.

---

Happy Dockering! 🚀