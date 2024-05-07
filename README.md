# Laravel Live Chat + Reverb

## Pre-requisites:
- PHP >= 8.2
- Composer
- MySQL >= 5.7
- Node.js >= 20
- Laravel 11.0.8

## Steps for installation

- Clone the repository, or download the zip file and extract it.

- Copy the `.env.example` file to `.env`:
```shell
cp .env.example .env
```

- Create a MySQL database and set the database credentials in the `.env` file:
```shell
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE="<database_name>"
DB_USERNAME="<username>"
DB_PASSWORD="<password>"
```

- Install the dependencies.
```shell
composer install
```

- Generate the application key.
```shell
php artisan key:generate
```

- Install Reverb Package
```shell
php artisan reverb:install
```

- Setup Reverb credentials in the `.env` file:
```shell
BROADCAST_CONNECTION=reverb

###

REVERB_APP_ID=
REVERB_APP_KEY=
REVERB_APP_SECRET=
REVERB_HOST="localhost"
REVERB_PORT=8080
REVERB_SCHEME=http

VITE_REVERB_APP_KEY="${REVERB_APP_KEY}"
VITE_REVERB_HOST="${REVERB_HOST}"
VITE_REVERB_PORT="${REVERB_PORT}"
VITE_REVERB_SCHEME="${REVERB_SCHEME}"
```

- Optimize the application cache.
```shell
php artisan optimize
```

- Run the migrations.
```shell
php artisan migrate:fresh
```

- Install the NPM dependencies.
```shell
npm install
```

- Build the assets.
```shell
npm run build
```

- **_[Optional]_** For development, run below command to watch the assets for changes.
```shell
npm run dev
```

- Start WebSocket server.
```shell
php artisan reverb:start
```

- Start listening to Queue jobs.
```shell
php artisan queue:listen
```

- Start the development server using below command or configure a virtual host.
```shell
php artisan serve
```