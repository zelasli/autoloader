# Zelasli Autoloader

Zelasli framework autoloader implementation.

## Using Loader

To use this class implementation follow this steps

### Include the Loader class file and register the loader.

```php
// Loader file include
require_once 'Loader.php';

// Initialize Loader class and boot it up
$loader = Loader::boot();

// Register Loader class as __autoload() implementation
$loader->register();
```

### Add the namespaces

```php
$loader->register_bucket("My\\Namespace", "/path/to/namespace");
```

### How it Works

```php
use My\Namespace\Book

$book = new Book()
```

The Loader class will look for a file `/path/to/namespace/Book.php` and include it for you.

### Including none class-based

To include php file that is not oop-based (functions and constants) php code. Firstly, create file in `/path/to/namespace/__index.php` and add this php code

```php
$loader->import("My\Namespace");
```

## Stop Loader

This will unregister Loader class as __autoload() implementation.

```php
$loader->stop();
```
