# M-Pesa SDK for PHP

M-Pesa SDK for PHP is an unofficial library aiming to help develbusinesses integrating every [M-Pesa](https://developer.mpesa.vm.co.mz) operations to their PHP applications.

## Contents

- [Features](#features)
- [Usage](#usage)
   - [Quickstart](#usage/scenario-1)
   - [Receive Money from a Mobile Account](#usage/scenario-1)
   - [Send Money to a Mobile Account](#usage/scenario-2)
   - [Send Money to a Business Account](#usage/scenario-3)
   - [Revert a Transaction](#usage/scenario-4)
   - [Query the Status of a Transaction](#usage/scenario-5)
   - [Examples](#usage/scenario-6)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
   - [Using Composer](#installation/scenario-1)
   - [Manual Installation](#installation/scenario-2)
- [Configuration](#configuration)
   - [Configuration Scenario 1](#configuration/scenario-1)
   - [Configuration Scenario 2](#configuration/scenario-2)
   - [Configuration Scenario 3](#configuration/scenario-3)
   - [Configuration Scenario 4](#configuration/scenario-4)
- [Related Projects](#related-projects)
   - [Dependencies](#related-projects/dependencies)
   - [Friends](#related-projects/friends)
   - [Alternatives](#related-projects/alternatives)
- [Contributing](#contributing)
- [Changelog](#changelog)
- [Authors](#authors)
- [Credits](#credits)
- [License](#license)

## Features <a name="features"></a>

- Receive money from a mobile account to a business account
- Send money from a business account to a mobile account
- Send money from a business account to a another business account
- Revert a transaction
- Query the status of a transaction

## Usage <a name="usage"></a>

### Quickstart <a name="#usage/scenario-1"></a>

### Receive Money from a Mobile Account <a name="#usage/scenario-2"></a>

```php
use Paymentsds\MPesa\Client;

$client = new Client([
   'apiKey' => '<REPLACE>',             // API Key
   'publicKey' => '<REPLACE>',          // Public Key
   'serviceProviderCode' => '<REPLACE>' // input_ServiceProviderCode
]);

$paymentData = [
   'from' => '841234567',       // input_CustomerMSISDN
   'reference' => '11114',      // input_ThirdPartyReference
   'transaction' => 'T12344CC', // input_TransactionReference
   'amount' => '10'             // input_Amount
];

$result = $client->receive($paymentData);

if ($result->success) {
   // Handle success
} else {
   // Handle failure
}
```

### Send Money to a Mobile Account <a name="#usage/scenario-3"></a>

```php
use Paymentsds\MPesa\Client;

$client = new Client([
   'apiKey' => '<REPLACE>',             // API Key
   'publicKey' => '<REPLACE>',          // Public Key
   'serviceProviderCode' => '<REPLACE>' // input_ServiceProviderCode
]);

$paymentData = [
   'to' => '841234567',         // input_CustomerMSISDN
   'reference' => '11114',      // input_ThirdPartyReference
   'transaction' => 'T12344CC', // input_TransactionReference
   'amount' => '10'             // input_Amount
];

$result = $client->send($paymentData);

if ($result->success) {
   // Handle success scenario
} else {
   // Handle failure scenario
}
```

### Send Money to a Business Account <a name="#usage/scenario-4"></a>

```php
use Paymentsds\MPesa\Client;

$client = new Client([
   'apiKey' => '<REPLACE>',             // API Key
   'publicKey' => '<REPLACE>',          // Public Key
   'serviceProviderCode' => '<REPLACE>' // input_ServiceProviderCode
]);

$paymentData = [
   'to' => '979797',         // input_ReceiverPartyCode
   'reference' => '11114',      // input_ThirdPartyReference
   'transaction' => 'T12344CC', // input_TransactionReference
   'amount' => '10'             // input_Amount
];

$result = $client->send($paymentData);

if ($result->success) {
   // Handle success scenario
} else {
   // Handle failure scenario
}
```

### Revert a Transaction <a name="#usage/scenario-5"></a>

```php
use Paymentsds\MPesa\Client;

$client = new Client([
   'apiKey' => '<REPLACE>',             // API Key
   'publicKey' => '<REPLACE>',          // Public Key
   'serviceProviderCode' => '<REPLACE>', // input_ServiceProviderCode
   'initiatorIdentifier' => '<REPLACE>', // input_InitiatorIdentifier,
   'securityIdentifier' => '<REPLACE>'  // input_SecurityCredential
]);

$paymentData = [
   'reference' => '11114',      // input_ThirdPartyReference
   'transaction' => 'T12344CC', // input_TransactionReference
   'amount' => '10'             // input_Amount
];

$result = $client->revert($paymentData);

if ($result->success) {
   // Handle success scenario
} else {
   // Handle failure scenario
}
```

### Query the Status of a Transaction <a name="#usage/scenario-6"></a>

```php
use Paymentsds\MPesa\Client;

$client = new Client([
   'apiKey' => '<REPLACE>',             // API Key
   'publicKey' => '<REPLACE>',          // Public Key
   'serviceProviderCode' => '<REPLACE>', // input_ServiceProviderCode
]);

$paymentData = [
   'subject' => '11114',      // input_QueryReference
   'reference' => 'T12344CC', // input_ThirdPartyReference
];

$result = $client->query($paymentData);

if ($result->success) {
   // Handle success scenario
} else {
   // Handle failure scenario
}
```

### Examples <a name="usage/scenario-7"></a>

## Prerequisites <a name="prerequisites"></a>

- [PHP 7.2+](https://www.php.net)
- [Composer](https://getcomposer.org)

## Installation <a name="installation"></a>

### Using Composer <a name="installation/scenario-1"></a>

```bash
composer require paymentsds/mpesa
```

### Manual Installation <a name="installation/scenario-2"></a>
```bash
git clone https://github.com/paymentsds/mpesa-php-sdk mpesa-php-sdk
cd mpesa-php-sdk
composer install
```

## Configuration <a name="configuration"></a>

### Configuration Scenario 1 <a name="configuration/scenario-1"></a>

### Configuration Scenario 2 <a name="configuration/scenario-2"></a>

### Configuration Scenario 3 <a name="configuration/scenario-3"></a>

## Related Projects <a name="related-projects"></a>

### Dependencies <a name="related-projects/dependencies"></a>

#### Production Dependencies

- [Guzzle](https://github.com/guzzle/guzzle)


#### Development Dependencies

- [Dependency 1](https://github.com/<username>/<project>)
- [Dependency 2](https://github.com/<username>/<project>)
- [Dependency 3](https://github.com/<username>/<project>)
- [Dependency 4](https://github.com/<username>/<project>)

### Friends <a name="related-projects/friends"></a>

- [M-Pesa SDK for Javascript](https://github.com/paymentsds/mpesa-js-sdk)
- [M-Pesa SDK for Ruby](https://github.com/paymentsds/mpesa-ruby-sdk)
- [M-Pesa SDK for Python](https://github.com/paymentsds/mpesa-python-sdk)


## Contributing <a name="contributing"></a>

## Changelog <a name="changelog"></a>

## Authors <a name="authors"></a>

- [Anísio Mandlate](https://github.com/AnisioMandlate)
- [Edson Michaque](https://github.com/edsonmichaque)
- [Elton Laice](https://github.com/eltonlaice)
- [Nélio Macombo](https://github.com/neliomacombo)

## Credits <a name="credits"></a>

- [All Contributors](../../contributors)

## License <a name="license"></a>

Copyright 2020 Anísio Mandlate, Edson Michaque, Elton Laice and Nélio Macombo

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

