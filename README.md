## 👋 Welcome to affine 🚀

Privacy-first, open-source workspace and knowledge base

## 📋 Description

Privacy-first, open-source workspace and knowledge base

## 🚀 Services

- **app**: ghcr.io/toeverything/affine-graphql:latest

### Infrastructure Components

- **redis**: Redis database
- **db**: Postgres database


## 📦 Installation

### Option 1: Quick Install
```bash
curl -q -LSsf "https://raw.githubusercontent.com/composemgr/affine/main/docker-compose.yaml" -o compose.yml
```

### Option 2: Git Clone
```bash
git clone "https://github.com/composemgr/affine" ~/.local/srv/docker/affine
cd ~/.local/srv/docker/affine
docker compose up -d
```

### Option 3: Using composemgr
```bash
composemgr install affine
```

## 🔧 Configuration

### Environment Variables

```shell
TZ=America/New_York
APP_ADMIN_USER=admin
APP_ADMIN_PASS=changeme_admin_password
DB_USER_NAME=affine
```

See `docker-compose.yaml` for complete list of configurable options.

## 🌐 Access

- **Web Interface**: http://172.17.0.1:61012

## 📂 Volumes

- `./rootfs/data/affine` - Data storage
- `./rootfs/config/affine` - Data storage
- `./rootfs/data/db/redis/affine` - Data storage
- `./rootfs/data/db/postgres/affine` - Data storage

## 🔐 Security

- Change all default passwords before deploying to production
- Use strong secrets for all authentication tokens
- Configure HTTPS using a reverse proxy (nginx, traefik, caddy)
- Regularly update Docker images for security patches
- Backup your data regularly

## 🔍 Logging

```shell
docker compose logs -f app
```

## 🛠️ Management

```bash
# Start services
docker compose up -d

# Stop services
docker compose down

# Update to latest images
docker compose pull && docker compose up -d

# View logs
docker compose logs -f

# Restart services
docker compose restart
```

## 📋 Requirements

- Docker Engine 20.10+
- Docker Compose V2+

## 🤝 Author

🤖 casjay: [Github](https://github.com/casjay) 🤖  
🦄 composemgr: [Github](https://github.com/composemgr) 🦄
