## PHP 7.4 + Mysql 8.0 + PhpMyAdmin + MailDev

### Getting started
clone or download this repo.

If you haven't installed docker yet, you can download it here: https://www.docker.com/products/docker-desktop

### Quickstart
To get started right away, run the following command in the root folder.

    Docker-compose up -d --build

After the images are build, the containers should have been started. After that you can use the following adres to reach the application: http://localhost:8080/

**MySQL**
When setting up the config for your CMS (like Wordpress, Joomla or Drupal) or framework (like Laravel), use `mysql-db` as hostname instead of *localhost*.

MySQL can be reached directly using a MySQL tool like MySQL workbench.
Host: `localhost`
Port: `8083`
Default username: `root`
Default password: `root`


**PhpMyAdmin**
PhpMyAdmin can be reached at: http://localhost:8081/
Default username: `root`
Default password: `root`

**Mail server**
When setting up the config for your CMS (like Wordpress, Joomla or Drupal) or framework (like Laravel), use `maildev` as hostname instead of *localhost* and port 25.

Maildev can be reached at: http://localhost:8082/

### Customize your setup
Copy the `.env.example` and rename it to `.env` in the root, this can be used to change some basic settings to docker like the default port (keep in mind changing the `PORT_PREFIX` will change the to above mentionend URLs).

### Using Composer
Composer is installed by default in this application.
To use composer in the docker container, open a terminal and go to the directory containing the docker files.
After that enter the following command to login to the webserver.

    docker-compose exec www bash

Now you loged in to the debian server running Apache and php.
From here you can run composer using:

    composer -V

To logout out from the docker press `ctrl+d` (Windows/Linux) or `cmd+d` (MacOS).


## Supported application
Known support applications 
- Wordpress
- Laravel
- Drupal