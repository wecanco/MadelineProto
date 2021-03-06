---
title: messages.getRecentStickers
description: messages.getRecentStickers parameters, return type and example
---
## Method: messages.getRecentStickers  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|hash|[int](../types/int.md) | Yes|


### Return type: [messages\_RecentStickers](../types/messages_RecentStickers.md)

### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
if (isset($token)) { // Login as a bot
    $MadelineProto->bot_login($token);
}
if (isset($number)) { // Login as a user
    $sentCode = $MadelineProto->phone_login($number);
    echo 'Enter the code you received: ';
    $code = '';
    for ($x = 0; $x < $sentCode['type']['length']; $x++) {
        $code .= fgetc(STDIN);
    }
    $MadelineProto->complete_phone_login($code);
}

$messages_RecentStickers = $MadelineProto->messages->getRecentStickers(['hash' => int, ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - messages.getRecentStickers
* params - `{"hash": int, }`



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/messages.getRecentStickers`

Parameters:

hash - Json encoded int



Or, if you're into Lua:

```
messages_RecentStickers = messages.getRecentStickers({hash=int, })
```

