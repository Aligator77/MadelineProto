---
title: account.updatePasswordSettings
description: account.updatePasswordSettings parameters, return type and example
---
## Method: account.updatePasswordSettings  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|---------------|----------|
|current\_password\_hash|[bytes](../types/bytes.md) | Yes|
|new\_settings|[account\_PasswordInputSettings](../types/account_PasswordInputSettings.md) | Yes|


### Return type: [Bool](../types/Bool.md)

### Can bots use this method: **NO**


### Errors this method can return:

| Error    | Description   |
|----------|---------------|
|EMAIL_UNCONFIRMED|Email unconfirmed|
|NEW_SALT_INVALID|The new salt is invalid|
|NEW_SETTINGS_INVALID|The new settings are invalid|
|PASSWORD_HASH_INVALID|The provided password hash is invalid|


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

$Bool = $MadelineProto->account->updatePasswordSettings(['current_password_hash' => 'bytes', 'new_settings' => account_PasswordInputSettings, ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/account.updatePasswordSettings`

Parameters:

current_password_hash - Json encoded bytes

new_settings - Json encoded account_PasswordInputSettings




Or, if you're into Lua:

```
Bool = account.updatePasswordSettings({current_password_hash='bytes', new_settings=account_PasswordInputSettings, })
```

