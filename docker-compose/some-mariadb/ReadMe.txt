ReadMe: Related Sample Commands

(Docker installation: https://docs.docker.com/engine/installation/linux/centos/)
(sudo usermod -aG docker $USER)
(docker-compose installation: https://docs.docker.com/compose/install/)

Before attaching local-host's disk path to a path on container, must give the rights/permissions as: chown -R 500:500 /var/local/data

docker run --name some-mariadb -v /home/centos/dbdata:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=MASK -p 3306:3306 -d mariadb:5.5

docker exec -it some-mariadb bash

mysql -u root -p
/var/lib/mysql : mysql -p DBName < DBNAMEFile.dump



docker run --name some-mariadb -v /home/centos/dbdata:/var/lib/mysql -e MYSQL_RANDOM_ROOT_PASSWORD=yes -d mariadb:5.5
docker run -it --link some-mariadb:mysql --rm mariadb:5.5 sh -c 'exec mysql -h 3306 -P 3306 -u root -p zeehejuchienakaoviecheishoexakee'

GENERATED ROOT PASSWORD: zeehejuchienakaoviecheishoexakee

PLEASE REMEMBER TO SET A PASSWORD FOR THE MariaDB root USER !
To do so, start the server, then issue the following commands:

'/usr/bin/mysqladmin' -u root password 'new-password'
'/usr/bin/mysqladmin' -u root -h  password 'new-password'

Alternatively you can run:
'/usr/bin/mysql_secure_installation'

which will also give you the option of removing the test
databases and anonymous user created by default.  This is
strongly recommended for production servers.
