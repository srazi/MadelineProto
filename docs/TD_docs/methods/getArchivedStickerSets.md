---
title: getArchivedStickerSets
description: Returns list of archived sticker sets
---
## Method: getArchivedStickerSets  
[Back to methods index](index.md)


Returns list of archived sticker sets

### Params:

| Name     |    Type       | Required | Description |
|----------|:-------------:|:--------:|------------:|
|is\_masks|[Bool](../types/Bool.md) | Yes|Pass true to return masks, pass false to return stickers|
|offset\_sticker\_set\_id|[long](../types/long.md) | Yes|Identifier of the sticker set from which return the result|
|limit|[int](../types/int.md) | Yes|Maximum number of sticker sets to return|


### Return type: [StickerSets](../types/StickerSets.md)

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

$StickerSets = $MadelineProto->getArchivedStickerSets(['is_masks' => Bool, 'offset_sticker_set_id' => long, 'limit' => int, ]);
```

Or, if you're into Lua:

```
StickerSets = getArchivedStickerSets({is_masks=Bool, offset_sticker_set_id=long, limit=int, })
```

