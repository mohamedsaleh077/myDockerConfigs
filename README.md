# The Best Global Docker Config I Made!
for Web Development and this Stuff **NOT PRODUCTION READY** I tried to follow all best practices as I could.

## What Included?
- .env file for default credentials
- PHP-FPM :9000
- XDEUB :9001
- composer
- NGINX :80 :443
    - ready for multiple domains and subdomains
    - Basic Rate Limit
    - Self-Signed SSL Certificate
    - HTTPS forced
    - Basic Security Headers
    - Workers
    - works fine with MVC
    - Compression for Requests
    - hide PHP version and NGINX version from the headers
    - should be fine with laravel ig
- PostgreSQL :5432
    - any .sql files in  `/postgre/init` will run when you build
    - health check
- PgAdmin :8081
    - starts only after health check for postgreSQL
- MySQL :3306
    - any .sql in `/mysql` will run with first build
- phpMyAdmin :8082
- Redis :6379
- volumes for data, and network groups all of them!

you can optimuze or get refrence from this files.

### Notes
- for subdomains that you setup in Nginx, add them to your local machine hosts file, for linux: `/etc/hosts`
```
127.0.0.1 www.example.com
127.0.0.1 api.example.com
```

- you can add git and clone you php project in `/php-fpm/Dockerfile`
- the file structure that is excpected for using it, it is example and you can edit it to fit your needs.
```
.
├── docker
└── website
    ├── admin
    │   ├── app
    │   │   └── file.php
    │   │   └── composer.json
    │   └── public
    │       └── index.php
    ├── app
    │   └── public
    │       └── index.php
    └── main
        └── public
            └── index.php
```
this is for our nginx example.