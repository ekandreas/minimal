# Minimal
Experimental approach minimal composer WordPress development environment

Requirements:
* PHP and a MySql-database
* PHP Composer

Step-by-step:
* Create an application folder and step into it: `mkdir minimal && cd minimal`
* Initialize a composer project: `composer init`
* Add the extra/wordpress-install-dir in `composer.json` Example in this repo.
```
"extra": {
    "wordpress-install-dir": "public/wp",
    "installer-paths": {
        "public/wp-content/themes/{$name}/": [
            "type:wordpress-theme"
        ],
        "public/wp-content/plugins/{$name}/": [
            "type:wordpress-plugin"
        ]
    }
}
```
* Add wpackagist to repositories in your composer.json:
```
"repositories": [
    {
        "type": "composer",
        "url": "https://wpackagist.org"
    }
]
```
* Install install requirements: `composer require composer/installers johnpbloch/wordpress`
* Install a theme `composer require wpackagist-theme/twentyseventeen` or use this repos minimal theme "Almost Nothing".
* Add required `public/index.php` and `public/wp-config.php` and modify your settings to reflect web server and database.
* Point webserver at ./public or start it within php: `php -S localhost:8000 -t public/`
* Now browse to the web started and do the famous 5-minutes install!

Next up!
* Disable auto update and edit in files from wp-admin
* Version management with .gitignore and versions
* Environment variables with .env

This is an example of a minimal composer based WordPress development environment.
We advise you to use Roots / Bedrock!

# WordCamp 2017

* PHP Deployer: https://deployer.org
* Bedrock: https://www.roots.io/bedrock
* Laravel Valet: https://laravel.com/docs/5.5/valet
* PHPCI: https://www.phptesting.org/
* GitLab: https://about.gitlab.com/
* Terminal: http://ohmyz.sh/
* WP CLI: http://wp-cli.org/
