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

## Usage

```php
<?php

$errors = $this->get('validator')->validate($entity);
if (count($errors) > 0) {
    $list = $this
        ->get('acme.validator.error_converter')
        ->constraintViolationListToArray($errors);
}
```
