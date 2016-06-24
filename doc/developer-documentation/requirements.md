# Developer documentation

## Requirements for running BackBee CMS

To run BackBee CMS, your system needs to fulfill to a list of requirements.

Here you will find the list of required and optional requirements.

### Required

Because BackBee CMS is built on top of Symfony components, these elements 
(PHP extensions) are required :

* ``JSON`` needs to be enabled
* ``ctype`` needs to be enabled
* ``mbstring`` needs to be enabled
* ``tokenizer`` needs to be enabled

The minimum version of PHP must be: **PHP 5.4.0**.

### Optional

* You (may) need to have the date.timezone setting defined in your PHP configuration
* You (may) need to have the PHP-XML module installed
* You (may) need to have at least version 2.6.21 of libxml
* You (may) need to have the GD module installed
* You (may) need to have iconv module enabled
* You (may) need to have POSIX enabled (only on *nix)
* You (may) need to have Intl installed with ICU 4+
* You (may) need to have APC 3.0.17+ installed (or another opcode cache needs to be installed)
* PHP configuration recommended settings:

```
short_open_tag = Off

magic_quotes_gpc = Off

register_globals = Off

session.auto_start = Off
```


### Doctrine2 (Database management)

Because we depend on Doctrine 2, you will need to have PDO extension installed.
Additionally, you need to have the associated PDO driver installed for the database server you want to use.

Also, for Unit Testing, you will need to have ``sqlite3`` and ``pdo_sqlite`` extensions enabled.



