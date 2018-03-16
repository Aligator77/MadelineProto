---
title: messages.getWebPagePreview
description: messages.getWebPagePreview parameters, return type and example
---
## Method: messages.getWebPagePreview  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|---------------|----------|
|message|[string](../types/string.md) | Yes|


### Return type: [MessageMedia](../types/MessageMedia.md)

### Can bots use this method: **NO**


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

$MessageMedia = $MadelineProto->messages->getWebPagePreview(['message' => 'string', ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/messages.getWebPagePreview`

Parameters:

message - Json encoded string




Or, if you're into Lua:

```
MessageMedia = messages.getWebPagePreview({message='string', })
```


## Return value 

If the length of the provided message is bigger than 4096, the message will be split in chunks and the method will be called multiple times, with the same parameters (except for the message), and an array of [MessageMedia](../types/MessageMedia.md) will be returned instead.


