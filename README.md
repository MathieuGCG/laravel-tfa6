# Laravel POS (TFA6)

A Point of Sale (POS) web application foundation built with Laravel for **IT0049 Web System Technologies**, demonstrating MVC architecture, routing, controllers, Eloquent ORM, database migrations, seeders, and Blade templating.

## Features & Routes

- **`/`** — Home page introducing the Laravel POS system
- **`/about`** — Overview of the application and technologies used
- **`/customers`** — Displays customer accounts retrieved from MySQL via the `Customer` Eloquent model
- **`/users`** — Displays system user accounts retrieved from MySQL via the `User` Eloquent model

## Database Schema

- **`customers`**: `id`, `full_name`, `email`, `phone`, `timestamps`
- **`users`**: `id`, `username` (unique), `full_name`, `timestamps`

Both tables are pre-populated with 5 sample records each using `Database\Seeders\PosSeeder`.

## Local Setup & Installation

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/MathieuGCG/laravel-tfa6.git](https://github.com/MathieuGCG/laravel-tfa6.git)
   cd laravel-tfa6
   ```

2. **Install PHP dependencies:**
   ```bash
   composer install
   ```

3. **Configure environment variables:**
   Copy `.env.example` to `.env` and generate an application key:
   ```bash
   cp .env.example .env
   php artisan key:generate
   ```

4. **Set up the MySQL database:**
   Create an empty MySQL database named `laravel_pos` (e.g., via phpMyAdmin), then update your `.env` file:
   ```env
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=laravel_pos
   DB_USERNAME=root
   DB_PASSWORD=

   SESSION_DRIVER=file
   ```

5. **Run migrations and database seeders:**
   ```bash
   php artisan migrate --seed
   ```

6. **Start the development server:**
   ```bash
   php artisan serve
   ```
   Open `http://127.0.0.1:8000` in your browser.