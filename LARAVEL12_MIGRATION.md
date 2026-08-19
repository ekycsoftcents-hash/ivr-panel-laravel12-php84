# Laravel 12 Migration Notes

This project has been upgraded from Laravel 5.7-era dependencies to **Laravel 12** with a Composer PHP constraint of `^8.2`, which includes **PHP 8.4**.

## Updated dependencies

The Composer manifest and lock file now use Laravel Framework 12, Laravel Tinker 2, Guzzle 7, the current AWS Laravel integration, Lab404 Laravel Impersonate 1.7, Yajra Laravel DataTables Oracle 12, FakerPHP, PHPUnit 11, Collision 8, and Laravel Pint. Deprecated packages such as `fideloper/proxy`, `webpatser/laravel-uuid`, `fzaninotto/faker`, and the legacy Yajra package were removed or replaced.

## Compatibility changes

The upgrade replaces removed Laravel helper calls used by configuration and factories, updates the proxy middleware to Laravel's built-in implementation, updates exception handler type declarations to `Throwable`, replaces the removed maintenance middleware class, removes a duplicate misplaced console kernel, converts malformed legacy bracket annotations into comments, and modernizes the PHPUnit configuration for PHPUnit 11.

## Installation

Use PHP 8.4 and install the project dependencies with:

```bash
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan storage:link
php artisan optimize
```

Configure the database, mail, AWS, telephony, and other service values in `.env` before running migrations or accessing authenticated features.

## Validation performed

The project successfully completed Composer dependency resolution, Composer manifest validation, optimized autoload generation, Laravel package discovery, PHP syntax linting for application/configuration/database/bootstrap/public PHP files, route listing with 147 routes, configuration caching, view caching, and platform requirement checks. The repository did not contain a `tests/Feature` directory, so the test suite has no application tests to execute yet.
