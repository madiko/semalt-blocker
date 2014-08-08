[![Build Status](https://travis-ci.org/nabble/semalt-blocker.svg?branch=master)](https://travis-ci.org/nabble/semalt-blocker)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/nabble/semalt-blocker/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/nabble/semalt-blocker/?branch=master)

semalt-blocker
==============

Block the nasty Semalt botnet from visiting your site and ruining your stats


## composer setup

This is the easiest method, but requires the use of [Composer](http://getcomposer.org). Add semalt-blocker to your
project by running the following in your terminal:

```shell
composer require nabble/semalt-blocker:dev-master
```

Then in your project add (but you probably already have this):

```php
require "vendor/autoload.php";
```

## legacy setup

Not using composer? No problem, copy the files `domains/blocked` and `compact/semaltblocker.php` to the same
directory in your project and add this line:

```php
require "/path/to/semaltblocker.php";
```


## basic usage

It's as easy as:

```php
<?php

\Nabble\Semalt::block();

// ... your app

```

Make sure you add it at the beginning of your code, it will save you!

## options

```php
\Nabble\Semalt::block(); // default, serve a 403 Forbidden response
\Nabble\Semalt::block('http://semalt.com'); // return them their own botnet traffic
\Nabble\Semalt::block('Hi, nasty bot'); // displays a nice message when blocked
```

## contribute

Yes, please!

Contribute by adding your list of known referral URL's used by Semalt in the file
[referrals](https://github.com/nabble/semalt-blocker/blob/master/tests/referrals) which is used in the unit tests.
When new URL's get added, the [domains](https://github.com/nabble/semalt-blocker/blob/master/domains) file needs updating
until all tests pass. This way we make sure new referrals are being blocked.

To contribute, please prepare a pull-request or contribute on this public Google Sheets file
[a.nabble.nl/semaltdoc](http://a.nabble.nl/semaltdoc).

## licence

MIT