## Skynix Magento 2 MySQL Cluster
# Installation Instructions

1. composer require skynix/m2-mysql-cluster
2. add configuration into app/etc/env.php

Section db -> connection -> default

add a new section:

'slave-servers' =>
   [
      0 =>
          [
                          'host' => '<mysql_slave_server>',
                          'dbname' => '<mysql_slave_db_name>',
                          'username' => '<mysql_user_name>',
                          'password' => '<mysql_user_pass>',
                          'model' => 'mysql4',
                          'engine' => 'innodb',
                          'initStatements' => 'SET NAMES utf8;',
                          'active' => '1',
           ]
   ]

Add there as many slave servers as you have.

3. bin/magento deploy:mode:set production
 
