# Reddit clone

## Run locally

```shell
$ docker-compose up -d

$ docker container ls
CONTAINER ID        IMAGE                    COMMAND                  CREATED             STATUS              PORTS                                            NAMES
969e74006af3        mailhog/mailhog:latest   "MailHog"                53 minutes ago      Up 53 minutes       0.0.0.0:1025->1025/tcp, 0.0.0.0:8025->8025/tcp   reddit-clone_mail_1
b41932431dac        mysql:8.0                "docker-entrypoint.s…"   3 hours ago         Up 3 hours          0.0.0.0:3306->3306/tcp, 33060/tcp                mysql_host
89d1041d118b        phpmyadmin/phpmyadmin    "/docker-entrypoint.…"   5 hours ago         Up 5 hours          0.0.0.0:8080->80/tcp                             test_phpmyadmin

$ export JAVA_HOME=`/usr/libexec/java_home -v 11`

$ java -version
openjdk version "11.0.8" 2020-07-14
OpenJDK Runtime Environment AdoptOpenJDK (build 11.0.8+10)
OpenJDK 64-Bit Server VM AdoptOpenJDK (build 11.0.8+10, mixed mode)

$ ./mvnw spring-boot:run
```

```shell
# user signup
$ curl --location --request POST 'http://localhost:8081/api/auth/signup' \
--header 'Content-Type: application/json' \
--data-raw '{
    "username": "TestUser",
    "email": "test@example.com",
    "password": "password"
}'
```

- access ([http://localhost:8025](http://localhost:8025)) and clicked mail content link
