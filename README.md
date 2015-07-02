# Simple Magento Maintenance Template

Simple template for magento maintenance mode and allow white listed ip to access the site when maintenance mode.

![Simple Magento Maintenance Template](https://goo.gl/cSmIs7)

## Installation

 - Download zip files
 - Extract files at your magento installation
 - For white listed ip addresses. Replace or backup your original `index.php` then use and rename the
 `index.php.simple` to `index.php`.
 - or, use and insert the code below in your `index.php` for whitelisted ip
```php 
/**
 * Maintenance mode
 */
$allowed_ip = array('127.0.0.12', '60.241.193.31');
if (file_exists(MAGENTO_ROOT.'/maintenance.flag') && !in_array($_SERVER['REMOTE_ADDR'], $allowed_ip)) {
    include_once __DIR__.'/errors/503.php';
    exit();
}
```


## License
This project is open-sourced software licensed under the [MIT license][mit-url].

[mit-url]: http://opensource.org/licenses/MIT