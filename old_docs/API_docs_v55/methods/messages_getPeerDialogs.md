---
title: messages.getPeerDialogs
description: messages.getPeerDialogs parameters, return type and example
---
## Method: messages.getPeerDialogs  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|---------------|----------|
|peers|Array of [Username, chat ID, Update, Message or InputPeer](../types/InputPeer.md) | Yes|


### Return type: [messages\_PeerDialogs](../types/messages_PeerDialogs.md)

### Can bots use this method: **NO**


### Errors this method can return:

| Error    | Description   |
|----------|---------------|
|CHANNEL_PRIVATE|You haven't joined this channel/supergroup|
|PEER_ID_INVALID|The provided peer id is invalid|


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

$messages_PeerDialogs = $MadelineProto->messages->getPeerDialogs(['peers' => [InputPeer, InputPeer], ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/messages.getPeerDialogs`

Parameters:

peers - Json encoded  array of InputPeer




Or, if you're into Lua:

```
messages_PeerDialogs = messages.getPeerDialogs({peers={InputPeer}, })
```

