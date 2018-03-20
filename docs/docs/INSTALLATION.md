# Installation

There are various ways to install MadelineProto:

* [Simple](#simple)
* [Simple (manual)](#simple-manual)
* [Composer from scratch](#composer-from-scratch)
* [Composer from existing project](#composer-from-existing-project)
* [Git](#git)


## Simple

```php
<?php
if (!file_exists('madeline.php')) {
    copy('https://phar.madelineproto.xyz', 'madeline.php');
}
require_once 'madeline.php';
```

This code will automatically download, auto-update and include MadelineProto.


## Simple (manual)

Download [madeline.php](https://phar.madelineproto.xyz/madeline.php), put it in the same directory as your script, and then put the following code in your PHP file:
```php
<?php
require_once 'madeline.php';
```

## Composer from scratch

composer.json:
```json
{
    "name": "pwrtelegram/pwrtelegram",
    "description": "Boosted version of telegram's bot API",
    "type": "project",
    "require": {
        "mhor/php-mediainfo": "^2.2",
        "danog/madelineproto": "dev-master"
    },
    "repositories": [
        {
            "type": "git",
            "url": "https://github.com/danog/phpseclib"
        }
    ],
    "minimum-stability": "dev",
    "license": "AGPL-3.0-only",
    "authors": [
        {
            "name": "Daniil Gentili",
            "email": "daniil.gentili.dg@gmail.com"
        }
    ],
    "autoload": {
        "psr-0": {
            "PWRTelegram\\PWRTelegram\\": "src/"
        }
    }
}
```

Then run:
```bash
composer update
```

Put the following code in your PHP file:
```
<?php
require_once 'vendor/autoload.php';
```

## Composer from existing project

Once you have all the requirements installed properly (on dev as well as production), add this to the ```composer.json``` file:

```
"repositories": [
    {
        "type": "git",
        "url": "https://github.com/danog/phpseclib"
    }
],
```

Make sure you also have these set in the composer.json:

```
"minimum-stability": "dev",
```

Then you can require the package by addding the following line to the require section:

```
"danog/madelineproto":"dev-master"
```



## git

Run the following commands in a console:

```
mkdir MadelineProtoBot
cd MadelineProtoBot
git init .
git submodule add https://github.com/danog/MadelineProto
cd MadelineProto
composer update
cp .env.example .env
cp -a *php tests userbots .env* ..
```

Now open `.env` and edit its values as needed.


