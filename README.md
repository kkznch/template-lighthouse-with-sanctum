# Template of Lighthouse with Laravel Sanctum

## Getting Started
### Prerequisites
- composer
    - https://getcomposer.org/

## Installation
1. Clone the repository
    ```sh
    $ git clone git@github.com:kkznch/template-lighthouse-with-sanctum.git
    $ cd template-lighthouse-with-sanctum
    ```
2. Copy env file
    ```sh
    $ cp .env.example .env
    ```
3. Install PHP packages
    ```sh
    $ composer install
    ```
4. Install PHP packages in the docker container
    ```sh
    $ docker run --rm \
        -u "$(id -u):$(id -g)" \
        -v $(pwd):/var/www/html \
        -w /var/www/html \
        laravelsail/php81-composer:latest \
        composer install --ignore-platform-reqs
    $ ./vendor/bin/sail artisan key:generate
    ```

# Commands
## Operation of the docker containers
- Start the docker containers
    ```sh
    $ ./vendor/bin/sail up -d
    ```
- Stop the docker containers
    ```sh
    $ ./vendor/bin/sail down
    ```

## Database fresh and seeding
- Fresh the database
    ```sh
    $ ./vendor/bin/sail artisan migrate:fresh
    ```
- Seed the database
    ```sh
    $ ./vendor/bin/sail artisan db:seed
    ```
- Fresh and seed the database
    ```sh
    $ ./vendor/bin/sail artisan migrate:fresh --seed
    ```    

## IDE helper
- Create IDE helper files
    ```sh
    $ ./vendor/bin/sail artisan lighthouse:ide-helper
    ```    
