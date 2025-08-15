# Settings package for Laravel

[![PHP Composer](https://github.com/Leromo-Dev/laravel-settings/actions/workflows/php.yml/badge.svg)](https://github.com/Leromo-Dev/laravel-settings/actions/workflows/php.yml)
[![Latest Version on Packagist](https://img.shields.io/packagist/v/leromo/laravel-settings.svg?style=flat-square)](https://packagist.org/packages/leromo/laravel-settings)
[![Total Downloads](https://img.shields.io/packagist/dt/leromo/laravel-settings.svg?style=flat-square)](https://packagist.org/packages/leromo/laravel-settings)

This package allows you to save settings in DB & Cache. You can use helper function to get settings value anywhere in a Laravel project like SnippetCMS.

* Database support
* Helper function
* Cache support

## Getting Started

### 1. Install

Run the following command:

```bash
composer require leromo/laravel-settings
```

### 2. Publish

Publish config file.

```bash
php artisan vendor:publish --provider="Leromo\LaravelSettings\SettingsServiceProvider" --tag=settings-config
```

### 3. Preparing the database

You need to publish the migration to create the media table:

```bash
php artisan vendor:publish --provider="Leromo\LaravelSettings\SettingsServiceProvider" --tag=settings-migration
```

After that, you need to run migrations.

```bash
php artisan migrate
```

### 4. Configure

You can change the options of your app from `config/laravel-settings.php` file

## Usage

### Helper

```php
setting()->get('promo');
setting()->get('promo', 'default');
setting()->put('promo', 'snippet');
setting()->delete('promo');
```

### Facade

```php
Setting::get('promo');
Setting::get('promo', 'default');
Setting::put('promo', 'snippet');
Setting::delete('promo');
```

## Testing

```bash
./vendor/bin/phpunit
```

## Changelog

Please see [Releases](../../releases) for more information what has changed recently.

## Contributing

Pull requests are more than welcome. You must follow the PSR coding standards.

## Security

If you discover any security related issues, please email leromo.dev@gmail.com instead of using the issue tracker.

## License

The MIT License (MIT). Please see [LICENSE](LICENSE.md) for more information.
