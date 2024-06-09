
npx create-strapi-app@latest my-project --quickstart

npm run develop
```bash
# File: ./docker-compose.yml

version: "3"
services:
postgres:
container_name: postgres
platform: linux/amd64 #for platform error on Apple M1 chips
env_file: .env
image: postgres:14.5-alpine
environment:
POSTGRES_USER: ${POSTGRES_USER}
POSTGRES_PASSWORD: ${POSTGRES_PASSWORD}
POSTGRES_DB: ${POSTGRES_DB}
volumes:
- ./_docker_volumes/postgres:/var/lib/postgresql/data
ports:
- "5432:5432"
```
docker-compose up -d postgres


```bash
docker-compose build strapi
```

```bash
docker-compose up strapi
```
