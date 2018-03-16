---
title: channels.getAdminedPublicChannels
description: channels.getAdminedPublicChannels parameters, return type and example
---
## Method: channels.getAdminedPublicChannels  
[Back to methods index](index.md)




### Return type: [messages\_Chats](../types/messages_Chats.md)

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

$messages_Chats = $MadelineProto->channels->getAdminedPublicChannels();
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/channels.getAdminedPublicChannels`

Parameters:




Or, if you're into Lua:

```
messages_Chats = channels.getAdminedPublicChannels({})
```

