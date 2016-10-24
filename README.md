InfyOm Laravel Generator
==============================

[![Total Downloads](https://poser.pugx.org/infyomlabs/laravel-generator/downloads)](https://packagist.org/packages/infyomlabs/laravel-generator)
[![Monthly Downloads](https://poser.pugx.org/infyomlabs/laravel-generator/d/monthly)](https://packagist.org/packages/infyomlabs/laravel-generator)
[![Daily Downloads](https://poser.pugx.org/infyomlabs/laravel-generator/d/daily)](https://packagist.org/packages/infyomlabs/laravel-generator)
[![Latest Stable Version](https://poser.pugx.org/infyomlabs/laravel-generator/v/stable)](https://packagist.org/packages/infyomlabs/laravel-generator)
[![Latest Unstable Version](https://poser.pugx.org/infyomlabs/laravel-generator/v/unstable)](https://packagist.org/packages/infyomlabs/laravel-generator)
[![License](https://poser.pugx.org/infyomlabs/laravel-generator/license)](https://packagist.org/packages/infyomlabs/laravel-generator)

Documentation is located [here](http://labs.infyom.com/laravelgenerator)


### Installation

```php
"require": {
	...
	"trungpv93/laravel-generator": "5.3.x-dev",
	"laravelcollective/html": "dev-master",
	"doctrine/dbal": "~2.3" //If you want to use Generate from Table option, you need to install
}
```

Run update compose

```sh
composer update
```

### Add Service Providers

```php
Collective\Html\HtmlServiceProvider::class,
Laracasts\Flash\FlashServiceProvider::class, //If Use Flash Notification
Prettus\Repository\Providers\RepositoryServiceProvider::class,
\InfyOm\Generator\InfyOmGeneratorServiceProvider::class,
```

### Add Aliases

```php
'Form'      => Collective\Html\FormFacade::class,
'Html'      => Collective\Html\HtmlFacade::class,
'Flash'     => Laracasts\Flash\Flash::class, //If Use Flash Notification
```

### Publish Vendor

```sh
php artisan vendor:publish
```

### Update API Routes

Open app\Providers\RouteServiceProvider.php and update mapApiRoutes method as following:

```php
Route::group([
    'middleware' => 'api',
    'namespace' => $this->namespace."\\API",
    'prefix' => 'api',
    'as' => 'api.',
], function ($router) {
    require base_path('routes/api.php');
});    
```

### Publish

```sh
php artisan infyom:publish
```	

### Run Publish Layout Command (Option)

```sh
php artisan infyom.publish:layout 
```
