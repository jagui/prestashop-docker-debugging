# PrestaShop Docker Debugging
Deploys prestashop on Docker with XDebug configured

## Why?

For a PrestaShop developer sometimes it's quite useful to debug some code on a plain vanila web. This set of Docker configuration files will spin a working instance in no time which can be easily debugged using PhpStorm

## What's inside

`docker-compose.yml` provides three services:

1. PrestaShop 1.6 running on Apache and Php-5.6.
    - Use the `prestashop\Dockerfile` to further customize the container. Here we're using XDebug 2.5.5 which is the highest version compatible with Php-5.6.
    - Note that running PrestaShop 1.6 on Php-7 will raise tons of warnings on the debugger, dramatically impacting the web performance.
  - You can further customize the Prestashop deployement by tweaking the `Environment` keys, check [https://github.com/PrestaShop/docker](PrestasShop/docker) for further reference. 
2. Standalone MariaDB instance that can be further inspected by..
3. ... a PhpMyAdmin instance


 ### How to run
 
 - `docker-compose up`
 - navigate to `http://prestashop.local` (remember to configure your hosts accordingly)
 - inspect the database in http://localhost:8080
 - `docker-compose down --volumes --remove-orphans` once you're done. Remember to delete the `.\fs` folder or you'll get an error when redeploying the containers.