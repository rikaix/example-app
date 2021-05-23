# example-app
laravel 8, docker 
#### Windows10 Home, local (docker desktop installed) : Laravel from docker with docker-compose (not sail),  
Ubuntu 20.04, maria-db, memcached, mailhog, volumes bridged

You can install a fresh copy and make your own change with :

`composer create-project laravel/laravel example-app` && `composer require laravel/sail --dev`

Or if you have laravel installer installed with:  
`composer global require laravel/installer`

`laravel new example-app && composer require laravel/sail --dev`

Sail is just required for the docker-compose.yml and Dockerfile files (robust ubuntu and php installation)

Based on the docker-compose.yml file from sail and the Dockerfile from vendor/laravel/sail/runtimes/8.0

changes in docker-compose.yml : WWWGROUP: '1000' AND WWWUSER: 'sail'

Start the first time with : `docker-compose up -d --build`

next, Start with : `docker-compose up -d`

Stop with : `docker-compose down` (stop and remove cont. )

`docker-compose pause` and `docker-compose unpause` (pause without removing cont. )

go and interact with the container with :  
`docker exec -it example-app_laravel.test_1 /bin/bash`  
or  
`docker exec -it example-app_laravel.test_1 /bin/sh`
