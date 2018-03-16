---
title: account.updateNotifySettings
description: Change notification settings
---
## Method: account.updateNotifySettings  
[Back to methods index](index.md)


Change notification settings

### Parameters:

| Name     |    Type       | Required | Description |
|----------|---------------|----------|-------------|
|peer|[InputNotifyPeer](../types/InputNotifyPeer.md) | Yes|The peers to which the notification settings should be applied|
|settings|[InputPeerNotifySettings](../types/InputPeerNotifySettings.md) | Yes|Notification settings|


### Return type: [Bool](../types/Bool.md)

### Can bots use this method: **NO**


### Errors this method can return:

| Error    | Description   |
|----------|---------------|
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

$Bool = $MadelineProto->account->updateNotifySettings(['peer' => InputNotifyPeer, 'settings' => InputPeerNotifySettings, ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/account.updateNotifySettings`

Parameters:

peer - Json encoded InputNotifyPeer

settings - Json encoded InputPeerNotifySettings




Or, if you're into Lua:

```
Bool = account.updateNotifySettings({peer=InputNotifyPeer, settings=InputPeerNotifySettings, })
```

