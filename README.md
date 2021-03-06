# Materialize for Yii2

This package integrates the Materialize CSS framework into [Yii2](http://www.yiiframework.com/).
[Materialize](http://materializecss.com/) is a modern responsive front-end framework based on Material Design.

See [official documentation](http://macgyer.github.io/yii2-materializecss/) for detailed information.

## Installation

The preferred way of installation is through Composer.
If you don't have Composer you can get it here: https://getcomposer.org/

To install the package add the following to the ```required``` section of your composer.json:
```
"require": {
    "macgyer/yii2-materializecss": "*"
},
```

## Usage

To load the Materialize CSS files integrate the MaterializeAsset into your app.
Two ways to achieve this is to register the asset in the main layout:

```php
// @app/views/layouts/main.php

\macgyer\yii2materializecss\assets\MaterializeAsset::register($this);
// further code
```

or as a dependency in your app wide AppAsset.php

```php
// @app/assets/AppAsset.php

public $depends = [
    'macgyer\yii2materializecss\assets\MaterializeAsset',
    // more dependencies
];
```

## Widgets

The following widgets are currently available:

* ActiveField
* ActiveForm
* Alert
* Breadcrumbs
* Button
* Chip
* DatePicker
* DetailView
* Dropdown
* Fixed Action Button
* GridView with ActionColumn
* Icon
* Modal
* Nav
* NavBar
* Progress
* Spinner
* SwitchButton

These widgets are planned for development:

* Collapsible
* Collection
* Toast

## Gii support

If you are creating your CRUD controller and view files using Gii you can get materialized view files by integrating the adapted Gii templates.

```php
// @app/config/main-local.php

$config['modules']['gii'] = [
    'class' => 'yii\gii\Module',      
    'allowedIPs' => ['127.0.0.1', '::1', '192.168.0.*', '192.168.178.20'],  
    'generators' => [
        'crud' => [
            'class' => 'yii\gii\generators\crud\Generator',
            'templates' => [ // setting materializecss templates
                'materializecss' => '@vendor/macgyer/yii2-materializecss/src/gii-templates/generators/crud/materializecss', 
            ]
        ]
    ],
];
```

You can copy those templates to any location you wish for further customization. Make sure you adapt the path accordingly in your config.

## Known issues

Yay, everything seems to be fine ...

## Sample layout

As of version 1.0.6 there is a sample layout file included in the package. You can use this file to get inspiration for
your own layout or replace the respective ```views/layouts/main.php``` with the file provided.

You can find the sample layout file in ```src/layout/main.php```.

## Change log

### 1.0.6 - 2016-05-16
* added sample layout
* fixed line separators
* removed Datepicker issue from section "Known issues"

### 1.0.5 - 2016-04-24
* updated README with fixed Datepicker issue
* refactored Breadcrumbs

### 1.0.3 - 2016-03-10
* fixed multiple usage of MaterializeWidgetTrait producing bugs
* updated PHPDoc in NavBar

### 1.0.2 - 2016-03-09
* added Spinner
* added Progress

### 1.0.1 - 2016-03-09
* updated README
* added Packagist support

### 1.0.0 - 2016-03-09
* Initial release
