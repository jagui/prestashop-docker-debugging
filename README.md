# PrestaShop Docker Debugging
Deploys prestashop on Docker with XDebug configured

## Why?

For a PrestaShop developer sometimes it's quite useful to debug some code on a plain vanila web. This set of Docker configuration files will spin a working instance in no time which can be easily debugged using PhpStorm

## What's inside

Two `docker-compose.yml` files, one  for PrestShop v1.6 and one for v1.7, each one providing three services:

1. PrestaShop running on Apache.
  - You can further customize the Prestashop deployement by tweaking the `Environment` keys, check [https://github.com/PrestaShop/docker](PrestasShop/docker) for further reference.
2. Standalone MariaDB instance that can be further inspected by..
3. ... a PhpMyAdmin instance


 ### How to run

On the corresponding PrestaShop version folder:
 - `docker-compose up`
 - navigate to `http://someshop.local` (remember to configure your hosts accordingly)
 - inspect the database in http://localhost:8080
 - `docker-compose down --volumes --remove-orphans` once you're done. Remember to delete the `.\fs` folder or you'll get an error when redeploying the containers.
