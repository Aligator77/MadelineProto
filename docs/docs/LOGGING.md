# Logging

MadelineProto provides a unified class for logging messages to the logging destination defined in [settings](SETTINGS.md).  

```
\danog\MadelineProto\Logger::log($message, $level);
```

`$message` is a string, an integer, an array, or any json-encodable object.  
`$level` is one of the following constants:
* `\danog\MadelineProto\Logger:FATAL_ERROR` - Indicates a fatal error
* `\danog\MadelineProto\Logger:ERROR` - Indicates a recoverable error
* `\danog\MadelineProto\Logger:NOTICE` - Indicates an info message
* `\danog\MadelineProto\Logger:VERBOSE` - Indicates a verbose info message
* `\danog\MadelineProto\Logger:ULTRA_VERBOSE` - Indicates an ultra verbose

By default, `$level` is `\danog\MadelineProto\Logger:NOTICE`.
