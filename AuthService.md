# Cgfort Auth Service

# Getting started

## Installation

Switch to the project folder

    cd project-folder

Install all the dependencies using composer

    composer install

Generate a new JWT authentication secret key (**This will update your .env file with something like JWT_SECRET=foobar**)

    php artisan jwt:secret

Run the database migrations (**Set the database connection in .env before migrating**)

    php artisan migrate

Run the documentation generate

    php artisan swagger-lume:generate
    
You can now access the docs at http://localhost:8000/api/documentation

Update social app config in  `config/services.php`

  ```php
    'facebook' => [
        'client_id' => '904926666686550',
        'client_secret' => 'f991c22e9ac0fb10f3fcc78462f75f67',
        'redirect' => ""
    ],

    'google' => [
        'client_id' => '398504279434-eeh8h7u5uetssci8i8sek8o5iirv0sg0.apps.googleusercontent.com',
        'client_secret' => 'oFVBRMRcUgPJA2RAZcGqzUdM',
        'redirect' => '',
    ],
  ```
  
Start the local development server

    php -S localhost:8000 -t public/

You can now access the server at http://localhost:8000

**TL;DR command list**

    composer install
    php artisan jwt:secret
    php artisan migrate
    php artisan swagger-lume:generate
    
**Make sure you set the correct database connection information before running the migrations** [Environment variables](#environment-variables)
    
----------

# Code overview

## Dependencies

- [jwt-auth](https://github.com/tymondesigns/jwt-auth) - For authentication using JSON Web Tokens
- [laravel/socialite](https://laravel.com/docs/8.x/socialite) - For authentication using social
- [darkaonline/swagger-lume](https://github.com/DarkaOnLine/SwaggerLume) - For generate docs for api

## Folders

- `app` - Contains all the Eloquent models
- `app/Http/Controllers` - Contains all the api controllers
- `app/Http/Middleware` - Contains the JWT auth middleware
- `config` - Contains all the application configuration files
- `database/factories` - Contains the model factory for all the models
- `database/migrations` - Contains all the database migrations
- `database/seeds` - Contains the database seeder
- `routes` - Contains all the api routes defined in web.php file
- `tests` - Contains all the application tests

## Environment variables

- `.env` - Environment variables can be set in this file

***Note*** : You can quickly set the database information and other variables in this file and have the application fully working.

----------

# Testing API

Run phpunit test

    vendor/bin/phpunit
    
Run the laravel development server

    php -S localhost:8000 -t public/

The api can now be accessed at

    http://localhost:8000

Request headers

| **Required** 	| **Key**              	| **Value**        
|----------	|------------------	|------------------	|
| Optional  | Content-Type     	| application/json 	|
| Optional 	| Authorization    	| Token {JWT}      	|

----------
 
# Authentication
 
This applications uses JSON Web Token (JWT) to handle authentication. The token is passed with each request using the `Authorization` header with `Token` scheme. The JWT authentication middleware handles the validation and authentication of the token. Please check the following sources to learn more about JWT.
 
- https://jwt.io/introduction/
- https://self-issued.info/docs/draft-ietf-oauth-json-web-token.html

----------
