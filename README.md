

<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

 # Prereqs
- mysql installed root access, no password for ease
- mysql -u root -p
- database: laravelnew


## Create NewProject
- cd /Users/amil/PhpstormProjects/
- composer create-project --prefer-dist laravel/laravel laravelnew
- ls
- cd laravelnew
- php artisan serve

## Routes
- routes/web.php

## Models:
- php artisan make:model Profile
- app/Profile.php
- Models represent your application's data structures and interact with the database.
- They encapsulate data access logic and provide methods for querying and manipulating data
- Models are typically associated with database tables and can define relationships with other models

## Database Migration and Seeding
- php artisan make:migration create_Profile
- /database/migrations/2024_04_15_202940_create__profile.php
- php artisan migrate
- Edit the `.env` file and use the correct database name in the `DB_DATABASE` key.
- mysql -u root -p


Laravel provides a migration system for managing database schema changes in a version-controlled manner.
You can create a new migration using Artisan

## Controllers:
- php artisan make:controller Profile
- app/Http/Controllers
- Controllers classes  handle requests and responses in app
- typically organize related request handling logic and interact with models to fetch or manipulate data.


## Views:
- resources/views
- Blade templating engine that are rendered and returned as HTTP responses. 
- contain the HTML markup and presentation logic of your application's user interface.
  with features like template inheritance, control structures, and more.


## Middleware:
- Middleware acts as a bridge between incoming HTTP requests and your application. It can intercept requests, perform actions, and modify responses.
- Laravel includes several middleware for common tasks like authentication, CSRF protection, and session management.


## Authentication and Authorization:
-php artisan make:auth
- Laravel makes it easy to implement user authentication and authorization with built-in features like authentication scaffolding, middleware, and access control lists (ACLs).
- You can generate authentication scaffolding using Artisan:

Validation:

Laravel provides powerful validation features to validate incoming HTTP request data before processing it. You can define validation rules and error messages for your request data.
RESTful Resource Controllers:

Laravel supports building RESTful APIs with resource controllers, which provide CRUD operations for resources like users, posts, etc.
You can generate a resource controller using Artisan:

php artisan make:controller ProfileController --resource
app/Http/Controllers

##  Artisan Command s
php artisan make:cast                        
php artisan make:channel                     
php artisan make:command                     
php artisan make:component                   
php artisan make:controller                  
php artisan make:event                       
php artisan make:exception                   
php artisan make:factory                     
php artisan make:job                         
php artisan make:listener                    
php artisan make:mail                        
php artisan make:middleware                  
php artisan make:migration                   
php artisan make:model                       
php artisan make:notification                
php artisan make:observer                    
php artisan make:policy                      
php artisan make:provider                    
php artisan make:request                     
php artisan make:resource                    
php artisan make:rule                        
php artisan make:seeder                      
php artisan make:test



## prereqs
##Opan Open
###MAC
brew update
brew install php
###LYNUX
sudo yum update
sudo yum install php
###windows
choco install php

###verify
php -v

## composer prereq
curl -sS https://getcomposer.org/installer -o composer-setup.php

php -r "if (hash_file('sha384', 'composer-setup.php') === 'EXPECTED_HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"

php composer-setup.php

sudo mv composer.phar /Users/amil/local/bin/composer
composer --version
composer diagnose
composer update





##  brew reinstall
brew reinstall php@7.2
brew services restart php@7.2

brew services start php
brew services restart php

## Brew setup
   brew update\n
   brew install php@7.2\n
     brew reinstall php@7.2\n
    LoadModule php7_module /opt/homebrew/opt/php@7.2/lib/httpd/modules/libphp7.so\n
     echo 'export PATH="/opt/homebrew/opt/php@7.2/bin:$PATH"' >> ~/.zshrc\n  echo 'export PATH="/opt/homebrew/opt/php@7.2/sbin:$PATH"' >> ~/.zshrc\n
   brew link --overwrite --force php@7.2\n

## php
php -S localhost:8000 -t public

## start mysql
brew install mysql
brew services start mysql
mysql -u root

ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '';
FLUSH PRIVILEGES;


sudo mysql.server start
pwd: evg123

access mysql: mysql -u root


superadmin
User::USERNAME			=> 'superadmin',
User::PASSWORD			=> Hash::make( 'SuperAdmin123!' ),

emiliano.gaytan@me.com
User::USERNAME			=> 'emiliano.gaytan@me.com',
User::PASSWORD			=> Hash::make( 'RomTech20#1' ),

## RESET & CLEANUP CACHE & DATABASE MIGRATION SCRIPTS (RUN ALL AT ONE TIME)
php artisan clear-compiled
composer dump-autoload
php artisan optimize
php artisan cache:clear
php artisan db:wipe
php artisan migrate
php artisan route:cache


## API docs:   Install & configue Steps for  https://github.com/mpociot/laravel-apidoc-generator
### 1. Install
composer require mpociot/laravel-apidoc-generator
cp vendor/mpociot/laravel-apidoc-generator/config/apidoc.php  ./config/

### 2. Configure Service in Lumen


#### 2.1. Register the service provider in your bootstrap/app.php:
$app->register( Mpociot\ApiDoc\ApiDocGeneratorServiceProvider::class);

#### 2.2 add to configure in  /bootstrap/app

$app->configure('apidoc');

#### execute to generate documentation
php artisan apidoc:generate




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
