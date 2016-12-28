# zend-expressive-hydrator-delegator

[![License](https://poser.pugx.org/tobias/zend-expressive-hydrator-delegator/license)](https://packagist.org/packages/tobias/zend-expressive-hydrator-delegator)
[![Latest Stable Version](https://poser.pugx.org/tobias/zend-expressive-hydrator-delegator/v/stable)](https://packagist.org/packages/tobias/zend-expressive-hydrator-delegator)
[![PHP 7 ready](http://php7ready.timesplinter.ch/tobias-trozowski/zend-expressive-hydrator-delegator/badge.svg)](https://travis-ci.org/tobias-trozowski/zend-expressive-hydrator-delegator)
[![Build Status](https://travis-ci.org/tobias-trozowski/zend-expressive-hydrator-delegator.svg?branch=master)](https://travis-ci.org/tobias-trozowski/zend-expressive-hydrator-delegator)
[![Coverage Status](https://coveralls.io/repos/tobias-trozowski/zend-expressive-hydrator-delegator/badge.svg?branch=master)](https://coveralls.io/r/tobias-trozowski/zend-expressive-hydrator-delegator?branch=master)
[![Total Downloads](https://poser.pugx.org/tobias/zend-expressive-hydrator-delegator/downloads)](https://packagist.org/packages/tobias/zend-expressive-hydrator-delegator)


Delegator for Zend [HydratorPluginManager](https://github.com/zendframework/zend-hydrator)

This package provides a delegator for the HydratorPluginManager which configures the PluginManager to use the service configuration from ```hydrators``` from your config.

The package is intended to be used with [Zend Expressive Skeleton](https://github.com/zendframework/zend-expressive-skeleton) or any other [Zend Expressive](https://github.com/zendframework/zend-expressive) application.


## Installation

The easiest way to install this package is through composer:

```bash
$ composer require tobias/zend-expressive-hydrator-delegator
```

## Configuration

In the general case where you are only using a single connection, it's enough to define the delegator factory for the HydratorManager:

```php
return [
    'dependencies' => [
        'delegators' => [
            'HydratorManager' => [
                \Tobias\Expressive\Hydrator\HydratorManagerDelegatorFactory::class,
            ],
        ],
    ],
];
```

### Using Expressive Config Manager

If you're using the [Expressive Config Manager](https://github.com/mtymek/expressive-config-manager) you can easily add the ConfigProvider class.

```php
$configManager = new ConfigManager(
    [
        \Tobias\Expressive\Hydrator\ConfigProvider::class,
    ]
);
```