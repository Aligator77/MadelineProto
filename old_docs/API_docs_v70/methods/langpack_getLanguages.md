---
title: langpack.getLanguages
description: langpack.getLanguages parameters, return type and example
---
## Method: langpack.getLanguages  
[Back to methods index](index.md)




### Return type: [Vector\_of\_LangPackLanguage](../types/LangPackLanguage.md)

### Can bots use this method: **NO**


### Errors this method can return:

| Error    | Description   |
|----------|---------------|
|LANG_PACK_INVALID|The provided language pack is invalid|


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

$Vector_of_LangPackLanguage = $MadelineProto->langpack->getLanguages();
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/langpack.getLanguages`

Parameters:




Or, if you're into Lua:

```
Vector_of_LangPackLanguage = langpack.getLanguages({})
```

