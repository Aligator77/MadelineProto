---
title: MadelineProto documentation
description: PHP implementation of telegram's MTProto protocol
---
# MadelineProto, a PHP MTProto telegram client

Do join the official channel, [@MadelineProto](https://t.me/MadelineProto) and the [support groups](https://t.me/pwrtelegramgroup)!


## What's this?

This library can be used to easily interact with Telegram **without** the bot API, just like the official apps.

It can login with a phone number (MTProto API), or with a bot token (MTProto API, **no bot API involved!**).

## Getting started

```
<?php

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

$MadelineProto->messages->sendMessage(['peer' => '@danogentili', 'message' => "Hi!\nThanks for creating MadelineProto! <3"]);
$MadelineProto->channels->joinChannel(['channel' => '@MadelineProto']);
```

Run this code in a browser or in a console.

## Documentation

- [Features](https://docs.madelineproto.xyz/FULL_README.html#features)
- [Full method list](https://docs.madelineproto.xyz/API_docs/methods)
- [How to use these methods](https://docs.madelineproto.xyz/FULL_README.html#methods)
- [Clicking inline buttons](https://docs.madelineproto.xyz/FULL_README.html#inline-buttons)
- [Uploading and downloading files](https://docs.madelineproto.xyz/FULL_README.html#uploading-and-downloading-files)
- [Changing settings](https://docs.madelineproto.xyz/FULL_README.html#settings)
- [Update management (getting incoming messages)](https://docs.madelineproto.xyz/FULL_README.html#handling-updates)
- [Using a proxy](https://docs.madelineproto.xyz/FULL_README.html#using-a-proxy)
- [Calls](https://docs.madelineproto.xyz/FULL_README.html#calls)
- [Secret chats](https://docs.madelineproto.xyz/FULL_README.html#secret-chats)
- [Storing sessions](https://docs.madelineproto.xyz/FULL_README.html#storing-sessions)
- [Exceptions](https://docs.madelineproto.xyz/FULL_README.html#exceptions)
- [Lua binding](https://docs.madelineproto.xyz/FULL_README.html#lua-binding)


## Very complex and complete examples

You can find examples for nearly every MadelineProto function in
* [`tests/testing.php`](https://github.com/danog/MadelineProto/blob/master/tests/testing.php) - examples for making/receiving calls, making secret chats, sending secret chat messages, videos, audios, voice recordings, gifs, stickers, photos, sending normal messages, videos, audios, voice recordings, gifs, stickers, photos.
* [`bot.php`](https://github.com/danog/MadelineProto/blob/master/bot.php) - examples for sending normal messages, downloading any media
* [`secret_bot.php`](https://github.com/danog/MadelineProto/blob/master/secret_bot.php) - secret chat bot
* [`multiprocess_bot.php`](https://github.com/danog/MadelineProto/blob/master/multiprocess_bot.php) - multithreaded bot
* [`magna.php`](https://github.com/danog/MadelineProto/blob/master/magna.php) - examples for receiving calls
* [`userbots/pipesbot.php`](https://github.com/danog/MadelineProto/blob/master/userbots/pipesbot.php) - examples for creating inline bots and using other inline bots via a userbot
* [`userbots/MadelineProto_bot.php`](https://github.com/danog/MadelineProto/blob/master/userbots/MadelineProto_bot.php) - Multi-function bot
* [`userbots/pwrtelegram_debug_bot`](https://github.com/danog/MadelineProto/blob/master/userbots/pwrtelegram_debug_bot.php) - Multi-function bot


