# Build Rails development environment with postgresql on docker

## Run this command to start developing rails
**You need to install dip gem if you didn't**

### Create new project
```
dip rails new . --database=postgresql
docker compose build app --no-cache
```

### update your config/database.yml
```
default: &default
  adapter: postgresql
  encoding: unicode
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  username: <%= ENV.fetch("POSTGRES_USER") %>
  password: <%= ENV.fetch("POSTGRES_PASSWORD") %>
  host: db
```

### Create your database
```
dip rails db:create
```

### Run your server
```
dip rails server
```
