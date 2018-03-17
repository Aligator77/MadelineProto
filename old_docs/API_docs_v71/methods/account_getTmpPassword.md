---
title: account.getTmpPassword
description: Get temporary password for buying products through bots
---
## Method: account.getTmpPassword  
[Back to methods index](index.md)


Get temporary password for buying products through bots

### Parameters:

| Name     |    Type       | Required | Description |
|----------|---------------|----------|-------------|
|password\_hash|[bytes](../types/bytes.md) | Yes|The password hash|
|period|[int](../types/int.md) | Yes|The validity period|


### Return type: [account\_TmpPassword](../types/account_TmpPassword.md)

### Can bots use this method: **NO**


### Errors this method can return:

| Error    | Description   |
|----------|---------------|
|PASSWORD_HASH_INVALID|The provided password hash is invalid|
|TMP_PASSWORD_DISABLED|The temporary password is disabled|


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

$account_TmpPassword = $MadelineProto->account->getTmpPassword(['password_hash' => 'bytes', 'period' => int, ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/account.getTmpPassword`

Parameters:

password_hash - Json encoded bytes

period - Json encoded int




Or, if you're into Lua:

```
account_TmpPassword = account.getTmpPassword({password_hash='bytes', period=int, })
```

