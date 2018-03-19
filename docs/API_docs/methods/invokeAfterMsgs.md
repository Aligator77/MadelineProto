---
title: invokeAfterMsgs
description: Result type returned by a current query.
---
## Method: invokeAfterMsgs  
[Back to methods index](index.md)


Result type returned by a current query.

### Parameters:

| Name     |    Type       | Required | Description |
|----------|---------------|----------|-------------|
|msg\_ids|Array of [long](../types/long.md) | Yes|List of messages on which a current query depends|
|query|[!X](../types/!X.md) | Yes|The query itself|


### Return type: [X](../types/X.md)

### Can bots use this method: **YES**


### Example:


```
if (!file_exists('madeline.php')) {
    copy('https://phar.madelineproto.xyz/madeline.php', 'madeline.php');
}
include 'madeline.php';

// !!! This API id/API hash combination will not work !!!
// !!! You must get your own @ my.telegram.org !!!
$api_id = 0;
$api_hash = '';

$MadelineProto = new \danog\MadelineProto\API('session.madeline', ['app_info' => ['api_id' => $api_id, 'api_hash' => $api_hash]]);
$MadelineProto->start();

$X = $MadelineProto->invokeAfterMsgs(['msg_ids' => [long, long], 'query' => !X, ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - invokeAfterMsgs
* params - `{"msg_ids": [long], "query": !X, }`



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/invokeAfterMsgs`

Parameters:

msg_ids - Json encoded  array of long

query - Json encoded !X




Or, if you're into Lua:

```
X = invokeAfterMsgs({msg_ids={long}, query=!X, })
```

