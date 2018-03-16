---
title: payments.getSavedInfo
description: payments.getSavedInfo parameters, return type and example
---
## Method: payments.getSavedInfo  
[Back to methods index](index.md)




### Return type: [payments\_SavedInfo](../types/payments_SavedInfo.md)

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

$payments_SavedInfo = $MadelineProto->payments->getSavedInfo();
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/payments.getSavedInfo`

Parameters:




Or, if you're into Lua:

```
payments_SavedInfo = payments.getSavedInfo({})
```

