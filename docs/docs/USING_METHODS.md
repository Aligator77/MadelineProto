# Using methods

A list of all of the methods that can be called with MadelineProto can be found here: [here (layer 75)](https://docs.madelineproto.xyz/API_docs/).

There are simplifications for many, if not all of, these methods.

* [Peers](#peers)
* [Files](FILES.md)
* [Secret chats](#secret-chats)
* [Entities (Markdown & HTML)](#entities)
* [reply_markup (keyboards & inline keyboards)](#reply_markup)
* [bot API objects](#bot-api-objects)
* [No result](#no-result)
* [Queues](#queues)

## Peers
[Full example](https://github.com/danog/MadelineProto/blob/master/bot.php)

If an object of type User, InputUser, Chat, InputChannel, Peer or InputPeer must be provided as a parameter to a method, you can substitute it with the user/group/channel's username (`@username`), bot API id (`-1029449`, `1249421`, `-100412412901`), or update.  

```
$MadelineProto->messages->sendMessage(['peer' => '@danogentili', 'message' => 'Testing MadelineProto...']);
```

## Secret chats
[Full example](https://github.com/danog/MadelineProto/blob/master/secret_bot.php)
If an object of type InputSecretChat must be provided as a parameter to a method, you can substitute it with the secret chat's id, the updateNewEncrypted message or the decryptedMessage:

```
$MadelineProto->messages->sendEncrypted(['peer' => $update, 'message' => ['_' => 'decryptedMessage', 'ttl' => 0, 'message' => 'Hi']]);
```


## Entities
[Full example](https://github.com/danog/MadelineProto/blob/master/tests/testing.php)
Methods that allow sending message entities ([messages.sendMessage](http://docs.madelineproto.xyz/API_docs/methods/messages_sendMessage.html) for example) also have an additional `parse_mode` parameter that enables or disables html/markdown parsing of the message to be sent.

```
$MadelineProto->messages->sendMessage(['peer' => '@danogentili', 'message' => '[Testing Markdown in MadelineProto](https://docs.madelineproto.xyz)', 'parse_mode' => 'Markdown']);
$MadelineProto->messages->sendMessage(['peer' => '@danogentili', 'message' => '<a href="https://docs.madelineproto.xyz">Testing HTML in MadelineProto</a>', 'parse_mode' => 'HTML']);
```



## reply_markup
reply_markup accepts bot API reply markup objects as well as MTProto ones.

```
$bot_API_markup = ['inline_keyboard' => [
        ['text' => 'MadelineProto docs', 'url' => 'https://docs.madelineproto.xyz'],
        ['text' => 'MadelineProto channel', 'url' => 'https://t.me/MadelineProto']
    ]
];
$MadelineProto->messages->sendMessage(['peer' => '@danogentili', 'message' => 'lel', 'reply_markup' => $bot_API_markup]);
```


## Bot API objects
To convert the results of methods to bot API objects you must provide a second parameter to method wrappers, containing an array with the `botAPI` key set to true.

```
$bot_API_object = $MadelineProto->messages->sendMessage(['peer' => '@danogentili', 'message' => 'lel'], ['botAPI' => true]);
```

MadelineProto also [supports bot API file IDs when working with files](FILES.md)


## No result
To disable fetching the result of a method, the array that must be provided as second parameter to method wrapper must have the `noResponse` key set to true.

```
$MadelineProto->messages->sendMessage(['peer' => '@danogentili', 'message' => 'lel'], ['noResponse' => true]);
```


## Call queues
Method calls may be executed at diferent times server-side: to avoid this, method calls can be queued:

```
$MadelineProto->messages->sendMessage(['peer' => '@danogentili', 'message' => 'lel'], ['queue' => 'queue_name']);
```

If the queue if the specified queue name does not exist, it will be created.
