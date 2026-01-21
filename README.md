## 👋 Welcome to affine 🚀

AFFiNE - Open-source alternative to Notion & Miro with local-first approach

## 📋 Description

AFFiNE is an open-source workspace combining docs, whiteboard, and databases. Write, draw, and plan all at once with a privacy-focused, local-first approach. Perfect alternative to Notion and Miro with real-time collaboration, AI features, and self-hosting capabilities.

## 🚀 Services

- **app**: AFFiNE GraphQL server (`ghcr.io/toeverything/affine-graphql:latest`)
- **redis**: Redis cache for sessions and background jobs
- **db**: PostgreSQL database for data storage

### Infrastructure Components

- **Database**: PostgreSQL for persistent storage
- **Cache/Queue**: Redis for caching and real-time features

## 📦 Installation

### Using curl
```shell
curl -q -LSsf "https://raw.githubusercontent.com/composemgr/affine/main/docker-compose.yaml" | docker compose -f - up -d
```

### Using git
```shell
git clone "https://github.com/composemgr/affine" ~/.local/srv/docker/affine
cd ~/.local/srv/docker/affine
docker compose up -d
```

### Using composemgr
```shell
composemgr install affine
```

## 🔧 Configuration

### Environment Variables

```shell
# Core Settings
TZ=America/New_York
BASE_HOST_NAME=${HOSTNAME}
BASE_DOMAIN_NAME=
PORT=80

# Admin Account
APP_ADMIN_USER=admin
APP_ADMIN_PASS=changeme_admin_password

# Database Settings
DB_USER_NAME=affine
DB_USER_PASS=changeme_db_password
DB_CREATE_DATABASE_NAME=affine

# Application Settings
AFFINE_SERVER_EXTERNAL_URL=https://${BASE_HOST_NAME}
TELEMETRY_ENABLE=false
NODE_ENV=production
```

## 🌐 Access

- **Web Interface**: http://172.17.0.1:61012
- **Admin Panel**: http://172.17.0.1:5555
- **Default Credentials**: admin@${BASE_DOMAIN_NAME} / changeme_admin_password

## 📂 Volumes

- `./rootfs/data/affine` - Application storage
- `./rootfs/config/affine` - Configuration files  
- `./rootfs/db/postgres/affine` - PostgreSQL data
- `./rootfs/db/redis/affine` - Redis data

## 🔐 Security

- Change default admin password immediately after first login
- All secrets use `changeme_*` prefix
- Telemetry disabled by default
- Database credentials isolated per deployment

## 🔍 Logging

```shell
docker compose logs -f app
docker compose logs -f db
docker compose logs -f redis
```

## 🛠️ Management

```shell
# Start
docker compose up -d

# Stop
docker compose down

# Update
docker compose pull && docker compose up -d

# Backup database
docker compose exec db pg_dump -U affine affine > backup.sql
```

## 📋 Requirements

- Docker Engine 20.10+
- Docker Compose V2+
- 2GB+ RAM recommended
- Reverse proxy for production

## 🤝 Author

🤖 casjay: [Github](https://github.com/casjay) 🤖  
🦄 composemgr: [Github](https://github.com/composemgr) 🦄
