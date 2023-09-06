#laravel #docker #sail

## Installing laravel sail app

- curl -s https://laravel.build/new-sail-application | bash
(This then creates a project dir called _new-sail-application_ (can be renamed)
- cd to the proj dir
- ./vendor/bin/sail up
- Gucci  
    

## (INSTALLING SAIL TO AN EXISTING APP)
You can also install Sail in an existing application using Composer, assuming your local development environment is set up to use it:
- composer require laravel/sail --dev
- php artisan sail:install
- publishes Sail’s docker-compose.yml file in your project directory
- ./vendor/bin/sail up

  

### Docker-compose.yml
every container holds one service only. This means that our Sail application comes with three services: one for PHP, one for MySQL, and a third for Redis.

If you open this file, you’ll see a services section with three components: laravel.test, mysql, and redis

laravel.test handles the PHP component and the other two handle what their names suggest.

Under the mySQL service (this service manages your database), you’ll find the image parameter, which indicates the image that this container is instantiating. Basically, an image is like the blueprint of a house while the container is the constructed house itself. 

All the images we need are sourced from [Docker Hub](https://hub.docker.com/), the largest image library on the net. They come with some documentation explaining how to use them. Check out the [documentation for MySQL here](https://hub.docker.com/_/mysql).

The ports parameter is used to sync your container port and local port. DB_PORT:-3306 is your local port and the line ${FORWARD_DB_PORT:-3306}:3306 syncs it with your container’s port.

Under environment, your database credentials are defined. They are currently pointing to values in the .env file located in the root directory of your project.

Docker uses volumes to persist (or save) data used by a container (even after the container is destroyed). Externalizing data or keeping data outside a container is important for a host of reasons.

Containers, by design, are created to be temporary. As such, when they crash or stop, all the data they hold is lost. When data is written to a volume and the container it belongs to is terminated, the data remains and can thus be used by a new container. Persistent data can also be shared by multiple containers on different machines.

The line volumes: - 'sailmysql:/var/lib/mysql' simply uses a volume named sailmysql to save all of the data in the var/lib/mysql directory (this is where our MySQL data is stored).

All the services on our container have to be connected to the same network to work together. The networks parameter specifies which internal network your container should use, in this case, sail.

Lastly, the healthcare parameter specifies the commands that Docker is to run to check your container’s health and ensure that it is working as expected.


php artisan serve --host=192.168.1.37  --port=4000

Related:
[[Sail Commands]]

