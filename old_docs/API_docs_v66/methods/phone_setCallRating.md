---
title: phone.setCallRating
description: phone.setCallRating parameters, return type and example
---
## Method: phone.setCallRating  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|---------------|----------|
|peer|[InputPhoneCall](../types/InputPhoneCall.md) | Yes|
|rating|[int](../types/int.md) | Yes|
|comment|[string](../types/string.md) | Yes|


### Return type: [Updates](../types/Updates.md)

### Can bots use this method: **NO**


### Errors this method can return:

| Error    | Description   |
|----------|---------------|
|CALL_PEER_INVALID|The provided call peer object is invalid|


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

$Updates = $MadelineProto->phone->setCallRating(['peer' => InputPhoneCall, 'rating' => int, 'comment' => 'string', ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/phone.setCallRating`

Parameters:

peer - Json encoded InputPhoneCall

rating - Json encoded int

comment - Json encoded string




Or, if you're into Lua:

```
Updates = phone.setCallRating({peer=InputPhoneCall, rating=int, comment='string', })
```

