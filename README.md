#Mailerlite API v2 wrapper for PHP

##Usage examples

#### Groups API

```php
require_once 'vendor/autoload.php';

$groupsApi = (new \MailerLiteApi\Mailerlite('your-api-key'))->groups();

$newGroup = $groupsApi->create(['name' => 'New group']); // creates group and returns it

$allGroups = $groupsApi->get(); // returns array of groups

$singleGroup = $groupsApi->find(123); // returns single item object

$groupsApi->delete(123); // deletes group
```

#### Multiple APIs at once

```php
require_once 'vendor/autoload.php';

$mailerliteClient = new \MailerLiteApi\Mailerlite('your-api-key');

$groupsApi = $mailerliteClient->groups();
$groups = $groupsApi->get(); // returns array of groups

$fieldsApi = $mailerliteClient->fields();
$fields = $fieldsApi->get(); // returns array of fields
```

##Use your preferred HTTP client

```php
require_once 'vendor/autoload.php';

$guzzle = new \GuzzleHttp\Client();
$guzzleClient = new \Http\Adapter\Guzzle6\Client($guzzle);

$mailerliteClient = new \MailerLiteApi\Mailerlite('your-api-key', $guzzleClient);
```
