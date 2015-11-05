# CookBooks
## Implement doctrine commands console
### Configuration :
To use doctrine command console in your Backbee project:

1. Create this structure in your app root folder :
```shell
/bin/doctrine
/bin/config/cli-config.php
/bin/src/bootstrap.php
```

Where `doctrine` is a symbolic link to the doctrine vendor command:
```shell
ln -s ../vendor/bin/doctrine
```

And `cli-config.php` contains the following code:
```php
<?php

// Doctrine CLI configuration file
use Doctrine\ORM\Tools\Console\ConsoleRunner;

require_once __DIR__ . '/../src/bootstrap.php';
return ConsoleRunner::createHelperSet($entityManager);
```

And `bootstrap.php` contains the following code:
```php
<?php

use Doctrine\ORM\Tools\Setup;

require_once "../vendor/autoload.php";
// Create a simple "default" Doctrine ORM configuration for XML Mapping
$isDevMode = true;
$config = Setup::createAnnotationMetadataConfiguration(array(__DIR__ . "/src"), $isDevMode);
// or if you prefer yaml or annotations
//$config = Setup::createXMLMetadataConfiguration(array(__DIR__."/config/xml"), $isDevMode);
//$config = Setup::createYAMLMetadataConfiguration(array(__DIR__."/config/yaml"), $isDevMode);
// database configuration parameters
$conn = array(
    'driver' => 'pdo_sqlite',
    'path' => __DIR__ . '/db.sqlite',
);
// obtaining the entity manager
$entityManager = \Doctrine\ORM\EntityManager::create($conn, $config);
```
You should then be able from the `bin` folder to use the doctrine console command:
```shell
#> ./doctrine
```
> For up-to-date `cli-config.php` and `bootstrap.php` files check the GIT repo @ https://github.com/doctrine/doctrine2-orm-tutorial.
