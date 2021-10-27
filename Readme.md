## PHP 7.4 + Mysql 8.0 + PhpMyAdmin + MailDev

### Getting started
clone or download this repo.

If you haven't installed docker yet, you can download it here: https://www.docker.com/products/docker-desktop

### Quickstart
To get started right away, run the following command in the root folder.

    Docker-compose up -d --build

After the images are build, the containers should have been started. After that you can use the following adres to reach the application: http://localhost:8080/

PhpMyAdmin can be reached at: http://localhost:8081/
Default username: `root`
Default password: `root`

Maildev can be reached at: http://localhost:8082/

### Customize your setup
The .env can be used to change some basic settings

