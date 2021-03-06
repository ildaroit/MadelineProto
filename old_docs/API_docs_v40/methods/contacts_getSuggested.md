---
title: contacts.getSuggested
description: contacts.getSuggested parameters, return type and example
---
## Method: contacts.getSuggested  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|---------------|----------|
|limit|[int](../types/int.md) | Yes|


### Return type: [contacts\_Suggested](../types/contacts_Suggested.md)

### Can bots use this method: **YES**


### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
$MadelineProto->session = 'mySession.madeline';
if (isset($token)) { // Login as a bot
    $MadelineProto->bot_login($token);
}
if (isset($number)) { // Login as a user
    $MadelineProto->phone_login($number);
    $code = readline('Enter the code you received: '); // Or do this in two separate steps in an HTTP API
    $MadelineProto->complete_phone_login($code);
}

$contacts_Suggested = $MadelineProto->contacts->getSuggested(['limit' => int, ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - contacts.getSuggested
* params - `{"limit": int, }`



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/contacts.getSuggested`

Parameters:

limit - Json encoded int




Or, if you're into Lua:

```
contacts_Suggested = contacts.getSuggested({limit=int, })
```

