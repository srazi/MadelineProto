---
title: editMessageReplyMarkup
description: Bots only. Edits message reply markup. Returns edited message after edit is complete server side
---
## Method: editMessageReplyMarkup  
[Back to methods index](index.md)


Bots only. Edits message reply markup. Returns edited message after edit is complete server side

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|chat\_id|[InputPeer](../types/InputPeer.md) | Yes|Chat the message belongs to|
|message\_id|[long](../types/long.md) | Yes|Identifier of the message|
|reply\_markup|[ReplyMarkup](../types/ReplyMarkup.md) | Yes|New message reply markup|


### Return type: [Message](../types/Message.md)

### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
if (isset($token)) { // Login as a bot
    $this->bot_login($token);
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

$Message = $MadelineProto->editMessageReplyMarkup(['chat_id' => InputPeer, 'message_id' => long, 'reply_markup' => ReplyMarkup, ]);
```

Or, if you're into Lua:

```
Message = editMessageReplyMarkup({chat_id=InputPeer, message_id=long, reply_markup=ReplyMarkup, })
```


## Usage of reply_markup

You can provide bot API reply_markup objects here.  


