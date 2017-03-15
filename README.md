# php-symfony-validator-converter

## Installation

Add requirement to composer:

```
composer require sokil/php-symfony-validator-converter
```

Add service to app or bundle services config:
```
acme.validator.error_converter:
  class: Sokil\Converter\ValidationErrorsConverter
```

Useage:
```php
<?php

$errors = $this->get('validator')->validate($order);
if (count($errors) > 0) {
    $list = $this
        ->get('normaizol.promo.validator.error_converter')
        ->constraintViolationListToArray($errors);
}
```
