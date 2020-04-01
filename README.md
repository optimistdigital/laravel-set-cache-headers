# Laravel SetCacheHeaders middleware

This Laravel package is a bug fix for not caching successful responses, especially the ones with the HTTP status code 204 (No Content).

See issue: https://github.com/laravel/framework/pull/32178

## Requirements

* Laravel 6.0+, probably works with older ones as well

## Usage

```
composer require optimistdigital/laravel-set-cache-headers
```

Swap out SetCacheHeaders middleware in `app/Http/Kernel.php` in your Laravel application:

Before:

```
    protected $routeMiddleware = [
        // ...
        'cache.headers' => \Illuminate\Http\Middleware\SetCacheHeaders::class,
        // ...
    ];
```

After

```
    protected $routeMiddleware = [
        // ...
        'cache.headers' => \OptimistDigital\SetCacheHeaders\Http\Middleware\SetCacheHeaders::class,
        // ...
    ];
```