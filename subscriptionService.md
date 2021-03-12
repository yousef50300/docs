# Cgfort Team Service

# Getting started

## Installation

Switch to the project folder

    cd project-folder

Install all the dependencies using composer

    composer install

Run the database migrations (**Set the database connection in .env before migrating**)

    php artisan migrate

Run the database seeders to seed plan

    php artisan db:seed
    
Run the documentation generate

    php artisan swagger-lume:generate
  
You can now access the docs at http://localhost:8000/api/documentation
    
Start the local development server

    php -S localhost:8000 -t public/

You can now access the server at http://localhost:8000

**TL;DR command list**

    composer install
    php artisan migrate
    php artisan swagger-lume:generate
    
**Make sure you set the correct database connection information before running the migrations** [Environment variables](#environment-variables)
    
----------

# Code overview

## Dependencies

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

Run the laravel development server

    php -S localhost:8000 -t public/

The api can now be accessed at

    http://localhost:8000

Request headers

| **Required** 	| **Key**              	| **Value**        
|----------	|------------------	|------------------	|
| Optional  | Content-Type     	| application/json 	|

----------
