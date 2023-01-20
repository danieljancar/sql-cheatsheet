## Installing SQL, RDBMS, and DBs on macOS 🍎

SQL, or Structured Query Language, is a programming language used for managing and manipulating relational databases. In order to use SQL on a macOS machine, you will need to install a relational database management system (RDBMS) such as MySQL, Oracle, or Microsoft SQL Server.

Here are some steps to help you get started with installing SQL and a RDBMS on a macOS machine:

1. Download and install a RDBMS of your choice, such as [MySQL](https://dev.mysql.com/downloads/mysql/) or [PostgreSQL](https://www.postgresql.org/download/macosx/).
2. Download and install a SQL client, such as [MySQL Workbench](https://dev.mysql.com/downloads/workbench/) or [pgAdmin](https://www.pgadmin.org/download/macos4/).
3. Once the installation is complete, you can start the SQL client and connect to your RDBMS.
4. You can also use additional tools such as [phpMyAdmin](https://www.phpmyadmin.net/) for web-based management of MySQL and MariaDB databases.

## Using Docker for SQL and RDBMS on macOS 🐳
Docker is a popular tool for containerizing applications and services. It can also be used to run a SQL server and RDBMS on a macOS machine. Here are some steps to help you get started with using Docker for SQL and RDBMS on a macOS machine:

1. Download and install [Docker for Mac](https://docs.docker.com/docker-for-mac/install/)
2. Search for and download a SQL server and RDBMS Docker image, such as [MySQL](https://hub.docker.com/_/mysql) or [PostgreSQL](https://hub.docker.com/_/postgres).
3. Start the Docker image and connect to it using a SQL client.
4. You can also use tools such as [phpMyAdmin](https://hub.docker.com/r/phpmyadmin/phpmyadmin/) for web-based management of your databases.

## Docker Code-Example
Option1:
```sql
    cd diretory/of/file (Usualy cd Downloads)
    docker ps
    docker cp file_name.bak sql:/tmp
```
Option2:
```sql
    docker cp /full/file/dir/with/file_name.bak sql:/tmp
```

## Different DBs for macOS 🍎
There are many different RDBMS and DBs available for macOS, such as MySQL, Oracle, Microsoft SQL Server, PostgreSQL, SQLite, and MariaDB. Each one has its own strengths and weaknesses, and the right choice for you will depend on your specific needs and use case.

- [MySQL](https://www.mysql.com/) is a popular, open-source RDBMS that is widely used in web applications and small to medium-sized businesses.
- [Oracle](https://www.oracle.com/database/) is a powerful, enterprise-level RDBMS that is widely used in large organizations and mission-critical applications.
- [PostgreSQL](https://www.postgresql.org/) is a powerful, open-source RDBMS that is known for its scalability and extensibility.
- [SQLite](https://www.sqlite.org/) is a lightweight, file-based RDBMS that is often used in embedded systems and mobile applications.
- [MariaDB](https://mariadb.org/) is a fork of MySQL and is often considered as an enhanced, open-source version of MySQL.

You can download and install any of these DBs as per your need and suitability. <br>
**Happy coding! 🚀**
