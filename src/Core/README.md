Spress Core - PHP Static site generator
=======================================

[![Build Status](https://travis-ci.org/spress/spress.png?branch=master)](https://travis-ci.org/spress/spress)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/spress/spress/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/spress/spress/?branch=master)
[![SensioLabsInsight](https://insight.sensiolabs.com/projects/1ea79d8e-894d-4cf5-8f64-c941376b3f77/mini.png)](https://insight.sensiolabs.com/projects/1ea79d8e-894d-4cf5-8f64-c941376b3f77)

Spress is a static site generator built with Symfony components and Twig as
default template engine. This repository is the core of Spress application.

Installation
------------
Go to your app folder and input the following command:

```batch
composer require spress/spress-core
```

How to use?
-----------
The entry-point class is `Yosymfony\Spress\Core\Spress`. The below example
point out how to use:

```php
use Yosymfony\Spress\Core\Spress;

class MyClass
{
    public function parseSite()
    {
        $spress = new Spress();
        $spress['spress.config.site_dir'] = '/path-to-your-spress-site';
        $spress->parse();
    }
}
```

### Including draft posts
```php
use Yosymfony\Spress\Core\Spress;

class MyClass
{
    public function parseSite()
    {
        $spress = new Spress();
        $spress['spress.config.site_dir'] = '/path-to-your-spress-site';
        $spress['spress.config.drafts'] = true;
        $spress->parse();
    }
}
```

### Another configuration values:

* `$spress['spress.config.env']`: Environment name `dev` by default. This option determines the configuration file in case you have a specific configuration file for that environment name. e.g: `$spress['spress.config.env'] = 'prod'`
* `$spress['spress.config.safe']`: With `true` disable all plugins. e.g: `spress['spress.config.safe'] = true`.
* `$spress['spress.config.drafts']`: Include draft posts in the transformation. `false` by default.
* `$spress['spress.config.url']`: Sets the URL base.
* `$spress['spress.config.timezone']`: Sets the timezone. E.g: "Europe/Madrid".

Unit tests
----------

Spress core uses [PHPUnit](https://phpunit.de) >= 5.7. You can run the unit tests with
the following command:

```bash
$ cd your-path
$ phpunit
```

License
-------

This library is available as open source under the terms of the
[MIT License](http://opensource.org/licenses/MIT).
