# How to Install Lumen in Laravel

1. Create a directory in laravel application called lumen

```
	lumen
		public
			.htaccess
			index.php
		config
			- api.php
			- jwt.php
		bootstrap.php 
```

2. Grab content from `bootstrap/app.php` and paste it into `lumen\bootstrap.php`

3. Replace  `App\Console\Kernel::class` with `App\Lumen\Console\Kernel::class`.

4. Comment out the current route `$app->group(['namespace' => 'App\Http\Controllers'],...`  and use the following route:

```php
$app->get('/', function () use ($app) {
    return $app->version();
});
```

5. Copy Lumen's `app` folder into Laravel's `app` folder as `Lumen`.

6. Update the namespace of `app/Lumen` folder to `namespace App\Lumen`.

7. In Laravel root folder, run `composer require laravel/lumen` to include Lumen package dependencies.

Now you may run in Laravel's public directory `php artisan serve` and Lumen's public folder `php -S localhost:9000` to serve both application. You should see Laravel and Lumen default.