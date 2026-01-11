FROM mysql:8.0.33
LABEL "project"="vprofile-project"
LABEL "Author"="Ben Ammar"

ENV MYSQL_ROOT_PASSWORD=vprodbpass
ENV MYSQL_DATABASE=accounts
ADD Docker-files/db/db_backup.sql  /docker-entrypoint-initdb.d/db_backup.sql


