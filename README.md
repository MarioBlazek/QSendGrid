# QSendgrid

Simple to use mailer, built with Sendgrid in the background.
Sends basic html email, with or without email attachments.

### Prerequisites

You will need to provide:
- Sendgrid API key, which can be created in [Sendgrid user interface](https://app.sendgrid.com/settings/api_keys)
- No Reply email address

> Key example: **SG.QDzWlz_gShWMVi8svP...**

### Installing

Install QSendgrid with composer:

```
composer require q-alliance/qsendgrid
```

## Basic usage

#### Sending basic html email:

```php
<?php

use QAlliance\QSendgrid;

// Create new QSendgrid object
$qs = new QSendgrid('NO_REPLY_EMAIL', 'SENDGRID_API_KEY');

// Send email to given address with given subject and content, returns bool
$result = $qs->send('to@example.com', 'My Subject', '<h1>This is a QSendgrid test email.</h1>');
```

#### Sending html email with attachments:

```php
<?php

use QAlliance\QSendgrid;

$attachmentUrls = [
	'./src/attachments/sample1.jpg',
	'./src/attachments/sample2.jpg'
];

// Create new QSendgrid object
$qs = new QSendgrid('NO_REPLY_EMAIL', 'SENDGRID_API_KEY');

// Send email to given address with given subject and content, returns bool
$result = $qs->send('to@example.com', 'My Subject', '<h1>This is a QSendgrid test email with attachments.</h1>', $attachmentUrls);
```

## Running the tests

Edit PHPUnit bootstrap file (**phpunit.bootstrap.php**) and add required values.
Run tests with this command:

 ```
 vendor/bin/phpunit --bootstrap phpunit.bootstrap.php
```

## Authors

* *Vicko Franic* - *Initial work* - [Github](https://github.com/vickofranic)