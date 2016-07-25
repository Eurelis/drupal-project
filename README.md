# Bootstraping a new Drupal 8 project

```
composer create-project eurelis/drupal-project DIRECTORY_PATH --repository="{\"type\":\"vcs\",\"url\":\"https://github.com/Eurelis/drupal-project\"}" --stability dev --prefer-dist --no-interaction
```

This will clone this repo and run composer install, you'll have the structure ready.

# Updating Drupal

Inside the `drupal` directory, run `composer update drupal/core --with-dependencies`

# Adding a Drupal module / theme / profile

Inside the `drupal` directory, run `composer require drupal/MODULE_NAME`.

By default if you do not provide a version it will get the latest stable one, minimum is dev if there is no stable release.

* Modules go to `drupal/www/modules/contrib`
* Themes go to `drupal/www/themes/contrib`
* Profiles go to `drupal/www/profiles/contrib`
* Drush extensions go to `drupal/drush/contrib`
* Other dependencies go to `drupal/vendor`

By default all the vendors are ignored by git (including the one cited above).

# DrupalVM

DrupalVM is included, if you want to use it rename `etc/example.config.yml` to `config.yml` and adapt to your project.
Developers can override this file by putting a local.config.yml next to it (for example on Windows you need to use `smb` instead of `nfs`)

[DrupalVM repo](https://github.com/geerlingguy/drupal-vm)

[DrupalVM Documentation](http://docs.drupalvm.com/en/latest/)

## Recommanded Vagrant plugins

Install them on commandline by using `vagrant plugin install PLUGINNAME`

* vagrant-cachier
* vagrant-hostmanager
* vagrant-auto_network

# Speed up your composer install

Install the following plugin globally : https://github.com/hirak/prestissimo

`composer global require "hirak/prestissimo:^0.3"`
