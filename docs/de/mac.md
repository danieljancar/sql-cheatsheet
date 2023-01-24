# Installation von SQL, RDBMS und DBs unter macOS 🍎

SQL oder Structured Query Language ist eine Programmiersprache zur Verwaltung und Bearbeitung relationaler Datenbanken. Um SQL auf einem macOS-Rechner zu verwenden, müssen Sie ein relationales Datenbankverwaltungssystem (RDBMS) wie MySQL, Oracle oder Microsoft SQL Server installieren.

Hier sind einige Schritte, die Ihnen beim Einstieg in die Installation von SQL und einem RDBMS auf einem macOS-Rechner helfen:

1. Laden Sie ein RDBMS Ihrer Wahl herunter und installieren Sie es, z. B. [MySQL](https://dev.mysql.com/downloads/mysql/) oder [PostgreSQL](https://www.postgresql.org/download/macosx /).
2. Laden Sie einen SQL-Client herunter und installieren Sie ihn, z. B. [MySQL Workbench](https://dev.mysql.com/downloads/workbench/) oder [pgAdmin](https://www.pgadmin.org/download/macos4/ ).
3. Sobald die Installation abgeschlossen ist, können Sie den SQL-Client starten und sich mit Ihrem RDBMS verbinden.
4. Sie können auch zusätzliche Tools wie [phpMyAdmin](https://www.phpmyadmin.net/) für die webbasierte Verwaltung von MySQL- und MariaDB-Datenbanken verwenden.

## Verwenden von Docker für SQL und RDBMS unter macOS 🐳
Docker ist ein beliebtes Tool zum Containerisieren von Anwendungen und Diensten. Es kann auch verwendet werden, um einen SQL-Server und RDBMS auf einem MacOS-Computer auszuführen. Hier sind einige Schritte, die Ihnen den Einstieg in die Verwendung von Docker für SQL und RDBMS auf einem macOS-Computer erleichtern:

1. Laden Sie [Docker für Mac] herunter und installieren Sie es (https://docs.docker.com/docker-for-mac/install/)
2. Suchen Sie nach einem SQL Server- und RDBMS-Docker-Image und laden Sie es herunter, z. B. [MySQL](https://hub.docker.com/_/mysql) oder [PostgreSQL](https://hub.docker.com/_ /postgres).
3. Starten Sie das Docker-Image und verbinden Sie sich mit einem SQL-Client damit.
4. Sie können auch Tools wie [phpMyAdmin](https://hub.docker.com/r/phpmyadmin/phpmyadmin/) für die webbasierte Verwaltung Ihrer Datenbanken verwenden.

## Docker Code-Example
> Lange version:
```cmd
    cd diretory/of/file (Usualy cd Downloads)
    docker ps
    docker cp file_name.bak sql:/tmp
```

> Kurze version:
```cmd
    docker cp /full/file/dir/with/file_name.bak sql:/tmp
```

## Verschiedene DBs für macOS 🍎
Es gibt viele verschiedene RDBMS und DBs für macOS, wie MySQL, Oracle, Microsoft SQL Server, PostgreSQL, SQLite und MariaDB. Jedes hat seine eigenen Stärken und Schwächen, und die richtige Wahl für Sie hängt von Ihren spezifischen Bedürfnissen und Ihrem Anwendungsfall ab.

- [MySQL](https://www.mysql.com/) ist ein beliebtes Open-Source-RDBMS, das in Webanwendungen und kleinen bis mittleren Unternehmen weit verbreitet ist.
- [Oracle](https://www.oracle.com/database/) ist ein leistungsstarkes RDBMS auf Unternehmensebene, das in großen Organisationen und geschäftskritischen Anwendungen weit verbreitet ist.
- [PostgreSQL](https://www.postgresql.org/) ist ein leistungsstarkes Open-Source-RDBMS, das für seine Skalierbarkeit und Erweiterbarkeit bekannt ist.
- [SQLite](https://www.sqlite.org/) ist ein leichtgewichtiges, dateibasiertes RDBMS, das häufig in eingebetteten Systemen und mobilen Anwendungen verwendet wird.
- [MariaDB](https://mariadb.org/) ist ein Fork von MySQL und wird oft als erweiterte Open-Source-Version von MySQL betrachtet.

Sie können jede dieser DBs je nach Bedarf und Eignung herunterladen und installieren. <br>
** Viel Spaß beim Programmieren! 🚀**