**Installing Laravel Projects**

1. Clone Laravel Project
2. Navigate pro directer & start docker container
_docker-compose up_
* If there is an error, run:
_lsof -i TCP:3306_
* If there is an app running on the port, kill the process, then run _docker-compose up again_
3. Create a ‘.env’ file in root dir of project
4. Install composer packages:
_composer install_
_composer update_
5. Generative encryption key for laravel
_php artisan key:generate_
6. Clear config cache:
_php artisan config:clear_
7. Run command to run migrations (make database tables)
_php artisan migrate_
8. Install necessary NPM packages:
_npm install_
9. Build assets for the Laravel application
_npm run build_
10. Start the tunneling (if you will show it to other peeps from other pcs)
_grok http 8000 —host-header=‘localhost:8000’_
(Skip some steps)
11. _php artisan serve_
*if you want to specify which host/url or port

php artisan serve --host=192.168.1.37  --port=4000