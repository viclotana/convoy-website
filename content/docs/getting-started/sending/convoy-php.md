---
title: Convoy PHP SDK
description: "Sending a webhook event with Convoy PHP SDK."
id: convoy-php
---

## Install Client
Install convoy-php, with:
```bash
$ composer require frain/convoy symfony/http-client nyholm/psr7
```

## Configure

```php[example]
use Convoy\Convoy;

$convoy = new Convoy(["api_key" => "your_api_key"]);
```

The SDK also supports authenticating via Basic Auth by defining your username and password.

```php[example]
$convoy = new Convoy(["username" => "default", "password" => "default"]);
```

In the event you're using a self hosted convoy instance, you can define the url as part of what is passed into convoy's constructor.

```php[example]
$convoy = new Convoy([
    "api_key" => "your_api_key",
    "uri" => "self-hosted-instance"
]);
```

## Create an Endpoint

```php[example]
$endpointData = [
    "url" => "https://0d87-102-89-2-172.ngrok.io",
    "description" => "Default Endpoint",
    "secret" => "endpoint-secret",
    "events" => ["*"]
]

$response = $convoy->endpoints()->create($appId, $endpointData);
$endpointId = $response['data']['uid'];
```

The next step is to create a subscription to the webhook source. Subscriptions are the conduit through which events are routed from a source to a destination on Convoy.

## Subscribe for Events

```php[example]
$subscriptionData = [
    "name" => "event-sub",
    "endpoint_id" => $endpointId
];

$response = $convoy->subscriptions()->create($subscriptionData);
```

With the subscription in place, you're set to send an event.

## Send an Event

To send an event, you'll need the `uid` from the application you created earlier.

```php[example]
$eventData = [
    "endpoint_id" => $endpointId,
    "event_type" => "payment.success",
    "data" => [
        "event" => "payment.success",
        "data" => [
            "status" => "Completed",
            "description" => "Transaction Successful",
            "userID" => "test_user_id808"
        ]
    ]
];

$response = $convoy->events()->create($eventData);
```

## Cheers! 🎉

You have successfully created a Convoy application to send events to your configured endpoint.
