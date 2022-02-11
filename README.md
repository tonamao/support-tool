## Support Tool
This is support-tool for [SameGame](https://github.com/tonamao/same-game-ci).

## Before start this...
git clone this repository.
cp .env.example .env
If necessary, fix .env to suit your environment.

## How to Start
TBD...

## How to Start with SameGame
Please refer to [SameGame](https://github.com/tonamao/same-game-ci) README.
It's a way to launch SameGame with support-tool.

After launch support-tool container, please follow the steps below.

1. In support container, generate application key.
```bash
$ docker-compose exec support sh
/var/www/support # php artisan key:generate
```
You can access `http://localhost:28080` .

2. In support container, execute commands to install admin library.
```bash
$ docker-compose exec support sh
/var/www/support # composer require encore/laravel-admin
/var/www/support # php artisan vendor:publish --provider="Encore\Admin\AdminServiceProvider"
/var/www/support # php artisan admin:install
```

You can access `http://localhost:28080/admin` .


## If error `Permission denied`
`chown 777 vendor`  
And execute this for the following directories.  
  
storage/framework/view  
storage/framework/session  
storage/framework/logs  
storage/framework/cache  


