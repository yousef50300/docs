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
    
Start the local development server

    php localhost:8000 -t public/

You can now access the server at http://localhost:8000

**TL;DR command list**

    composer install
    php artisan jwt:secret
    php artisan migrate
    php artisan swagger-lume:generate
    
**Make sure you set the correct database connection information before running the migrations** [Environment variables](#environment-variables)

    php artisan migrate
    php artisan serve
    
## API Specification

This application adheres to the api specifications set by the [Thinkster](https://github.com/gothinkster) team. This helps mix and match any backend with any other frontend without conflicts.

> [Full API Spec](https://github.com/gothinkster/realworld/tree/master/api)

More information regarding the project can be found here https://github.com/gothinkster/realworld

----------

# Code overview

## Dependencies

- [jwt-auth](https://github.com/tymondesigns/jwt-auth) - For authentication using JSON Web Tokens
- [laravel-cors](https://github.com/barryvdh/laravel-cors) - For handling Cross-Origin Resource Sharing (CORS)

## Folders

- `app` - Contains all the Eloquent models
- `app/Http/Controllers/Api` - Contains all the api controllers
- `app/Http/Middleware` - Contains the JWT auth middleware
- `app/Http/Requests/Api` - Contains all the api form requests
- `app/RealWorld/Favorite` - Contains the files implementing the favorite feature
- `app/RealWorld/Filters` - Contains the query filters used for filtering api requests
- `app/RealWorld/Follow` - Contains the files implementing the follow feature
- `app/RealWorld/Paginate` - Contains the pagination class used to paginate the result
- `app/RealWorld/Slug` - Contains the files implementing slugs to articles
- `app/RealWorld/Transformers` - Contains all the data transformers
- `config` - Contains all the application configuration files
- `database/factories` - Contains the model factory for all the models
- `database/migrations` - Contains all the database migrations
- `database/seeds` - Contains the database seeder
- `routes` - Contains all the api routes defined in api.php file
- `tests` - Contains all the application tests
- `tests/Feature/Api` - Contains all the api tests

## Environment variables

- `.env` - Environment variables can be set in this file

***Note*** : You can quickly set the database information and other variables in this file and have the application fully working.

----------

# Testing API

Run the laravel development server

    php artisan serve

The api can now be accessed at

    http://localhost:8000/api

Request headers

| **Required** 	| **Key**              	| **Value**            	|
|----------	|------------------	|------------------	|
| Yes      	| Content-Type     	| application/json 	|
| Yes      	| X-Requested-With 	| XMLHttpRequest   	|
| Optional 	| Authorization    	| Token {JWT}      	|

Refer the [api specification](#api-specification) for more info.

----------
 
# Authentication
 
This applications uses JSON Web Token (JWT) to handle authentication. The token is passed with each request using the `Authorization` header with `Token` scheme. The JWT authentication middleware handles the validation and authentication of the token. Please check the following sources to learn more about JWT.
 
- https://jwt.io/introduction/
- https://self-issued.info/docs/draft-ietf-oauth-json-web-token.html

----------
