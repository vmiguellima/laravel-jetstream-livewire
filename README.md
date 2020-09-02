# Laravel JetStream Livewire Starter Project

This is a starter project for the new laravel package JetStream introduced on Laracon.
It also provide some help setting/using JetStream

## Instalation

1. Setup environment
    1. Create **.env** file
    ```cp .env.example .env```
    <br>
    2. Generate a new key:
    ```php artisan key:generate```
    <br>


1. Install composer dependencies:
    ```composer install```
    <br>
2. Install npm dependencies and build dev:
    ```npm install && npm run dev```

### Database setup

Setup your database connection.
Update your **.env** with your databse:
- Driver
- URL
- Port
- Name
- User
- Password

After setup your databse connection run ```php artisan migrate```

You can start the server using ```php artisan serve```

## JetStream Options

### Setup Permissions

You can setup the permissons of your application.

Go to file, ```app/Providers/JetstreamServiceProvider.php```

On method ```configurePermissions()```, is where you will setup your permission.

#### Setup Api Tokens Permissions
You can add permissions to JetStream like this:

```php
Jetstream::permissions([
    'create',
    'delete',
    'update',
    'read',
    'create:server'
]);
```

### Team Options

#### Setup Roles

To can setup the roles of your application.

Go to file, ```app/Providers/JetstreamServiceProvider.php```

On method ```configurePermissions()```, is where you will setup your roles.

**Add New Role**

You can setup the role: 
- key
- name
- permissions
- description.

```php
Jetstream::role('editor', 'Editor', [
    'read',
    'create',
    'update',
])->description('Editor users have the ability to read, create, and update.');
```

```role(string $key, string $name, array $permissions)```

## Available Jetstream Features

Jetstream comes with 3 deafult featurs:

```php
Features::profilePhotos(), // add ability to have profile pictures
Features::api(), // add ability to generate api tokens
Features::teams(), // add ability to have teams
```


## Enable/Disable Jetstream Features

To enable or disable Jetstream Features you just need to open your **jetstream.php** config file, and comment or uncomment the features on *features*

```php
'features' => [
    Features::profilePhotos(),
    Features::api(),
    Features::teams(),
]
```


<hr>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 1500 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Cubet Techno Labs](https://cubettech.com)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[Many](https://www.many.co.uk)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com)**
- **[OP.GG](https://op.gg)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
