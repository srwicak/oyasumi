# Oyasumi API 😴🌙

Rails API application for sleep tracking.

## 🛠 Tech Stack
- **Framework**: Ruby on Rails 8(.0.2.1)
- **Database**: PostgreSQL 17 (Development)
- **Cache/Queue**: Redis 8 (Development)
- **Server**: Puma
- **Containerization**: Docker & Docker Compose

## 📋 Prerequisites

- Docker & Docker Compose
- Git

## 🚀 Quick Start

### Development Setup

1.  **Clone the repository**
    ```bash
    git clone https://github.com/srwicak/oyasumi.git
    cd oyasumi
    ```

2.  **Copy environtment file**
    ```bash
    cp docker/dev.envexample docker/dev.env
    ```

3.  **Start the application with Docker Compose**
    ```bash
    docker-compose -f docker-compose.dev.yml up --build
    ```

4.  **Access the application***
    - API: http://localhost:3000
    - Health check: http://localhost:3000/up

## 🔧 Development Commands

### Using Docker Compose

```bash
# Start services
docker-compose -f docker-compose.dev.yml up

# Start in background
docker-compose -f docker-compose.dev.yml up -d

# View logs
docker-compose -f docker-compose.dev.yml logs -f api

# Stop services
docker-compose -f docker-compose.dev.yml down

# Rebuild containers
docker-compose -f docker-compose.dev.yml up --build

# Access Rails console
docker-compose -f docker-compose.dev.yml exec api bundle exec rails console

# Generate the OpenAPI JSON file
docker-compose -f docker-compose.dev.yml run --rm api bash -lc "rake rswag:specs:swaggerize"
```

## 🌐 API Endpoints

### Health Check
- `GET /up` - Application health status

## 🔒 Environment Variables

Key environment variables in `docker/dev.env`:

```env
RAILS_ENV=development
POSTGRES_USER=<your-postgres-user - for example: oyasumi>
POSTGRES_PASSWORD=<your-postgres-password - for example: oyasumi>
POSTGRES_DB=<your-postgres-db - for example: oyasumi_development>
POSTGRES_HOST=<your-postgres-db - for example: db>
POSTGRES_PORT=<your-postgres-port - for example: 5432>
REDIS_URL=<your-redis-url for example: redis://redis:6379/1>
```