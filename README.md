planck-thatsme
==============

About me demo application.

## Documentation

Installation | Setup | Configuration | Usage | Upgrading

> Demo, Screenshot

### Getting started

Create environment config

    cp .env-dist .env

Build images

    docker-compose build
    
Inital setup of application    

    docker-compose run --rm -e APP_ADMIN_PASSWORD=admin1 php yii app/setup
        
Start stack
        
    docker-compose up -d

### Extend
    
    docker cp planck_php_1:/app/composer.json .
    docker cp planck_php_1:/app/composer.lock .
    docker cp planck_php_1:/app/src/app.env ./src

    composer update
    
    edit Dockerfile
    
    docker-compose build

### Customize

Adjust config

    return [
        'aliases' => [
            '@aye/frontend' => '@app/modules/frontend'
        ],
        'modules' => [
            'frontend' => [
                'class' => 'aye\frontend\Module'
            ]
        ]
    ];

Create bash    
    
    docker-compose run --rm -e YII_ENV=dev php bash

Create module    
    
    $ yii gii/module --moduleID=frontend --moduleClass=aye\\frontend\\Module

Create additional controller

    $ yii gii/controller \
        --controllerClass=aye\\frontend\\controllers\\ExamplesController \
        --viewPath=@aye/frontend/views/examples

### Deploy

    REGISTRY_HOST

## Support


## Contribute


## License


## Resources

- links

---

Built by
