SQL_CONFIGS
 
      /etc/mysql/mysql.conf.d/mysqld.cnf'
SQL_SHELL

    mysql -u USER -pPASSWORD -hmysql
SQL IMPORT:

    cat inputdump.sql | docker exec -i SQL_CONTAINER_ID /usr/bin/mysql -u USER -pPASSWORD DATABASE
SQL EXPORT:

    docker exec -i SQL_CONTAINER_ID /usr/bin/mysqldump -u USER -pPASSWORD DATABASE > outputdump.sql
SQL_CREATE_USER

      CREATE USER 'USER'@'localhost' IDENTIFIED BY 'PASSWORD';
   

      GRANT ALL PRIVILEGES ON * . * TO 'USER'@'localhost';


      FLUSH PRIVILEGES;
SQL_CHECK_USERS

    SELECT user,host FROM mysql.user;