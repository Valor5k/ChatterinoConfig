# Filters

##### Sub Only - Shows messages sent by subscribers to the channel.
```
author.subbed
```

##### Highlighted Only - Shows messages highlighted by your Chatterino settings.
```
flags.highlighted
```

##### ------------Clean Chat------------ Combines NO System Messages, No Bots, No Commands, NO Links, and NO Transcibinbg into one filter.
```
!message.content match r"(https?:\/\/|steam:\/\/)" && !message.content match r"^(!|%|&|\*|`|~|;|m!|\\|/|@@)" && !message.content match r"^\[.*] peepoTalk.*ImTalking" && !flags.system_message && !author.name match r"^(SchnozeBot|RibCrush|PhantomBot|Wizebot|Coebot|Moobot|Nightbot|StreamElements|Fossabot|ThePositiveBot|SupiBot)$"
```

##### NO Bots - Removes common bot accounts by their name. You can add bot accounts you see by adding their name seperated by "|" (Case Sensitive).
```
!author.name match r"^(SchnozeBot|RibCrush|PhantomBot|Wizebot|Coebot|Moobot|Nightbot|StreamElements|Fossabot|ThePositiveBot|SupiBot)$"
```

##### NO Links - Removes messages containing links.
```
!message.content match r"(https?:\/\/|steam:\/\/)"
```

##### NO Commands - Removes messages starting with common command characters such as "!uptime". Add or remove as you want, seperated by "|". These characters: + . * ? ^ $ ( ) [ ] { } | \ are special and must be preceded by "\\" eg. "\\$" = "$".
```
!message.content match r"^(!|%|&|\*|`|~|;|m!|\\|/|@@)"
```

##### NO Transcribing - Removes the spam transcribing the brodcaster in all languages.
```
!message.content match r"^\[.*] peepoTalk.*ImTalking"
```

##### NO System Messages - Removes system messages such as subsciptions and timeouts, you will still see messages sent with subscriptions.
```
!flags.system_message
```

##### -------------Anti Spam------------- Combines NO Repetitive Spam and NO one Word Spam into one filter.
```
!message.content match r"(\b\S{2,}\b)(.*\b\1\b){4,}|^(?!.*https?:\/\/)(?!.*steam:\/\/)\S{35,}" && !message.content match r"^(\S+)$"
```

##### NO Repetitive Spam - Removes messages with words repeated 5 or more times, or words over 35 characters long not including links.
```
!message.content match r"(\b\S{2,}\b)(.*\b\1\b){4,}|^(?!.*https?:\/\/)(?!.*steam:\/\/)\S{35,}"
```

##### NO One Word Spam - Removes messages containing only one word.
```
!message.content match r"^(\S+)$"
```

##### -----------Show Filtered----------- Combines Cleaned Messages, Repetative Spam, and One Word Spam into one filter.
```
message.content match r"^(\S+)$" || message.content match r"(\b\S{2,}\b)(.*\b\1\b){4,}|^(?!.*https?:\/\/)(?!.*steam:\/\/)\S{35,}" || message.content match r"(https?:\/\/|steam:\/\/)" || message.content match r"^(!|%|&|\*|`|~|;|m!|\\|/|@@)" || message.content match r"^\[.*] peepoTalk.*ImTalking" || flags.system_message || author.name match r"^(SchnozeBot|RibCrush|PhantomBot|Wizebot|Coebot|Moobot|Nightbot|StreamElements|Fossabot|ThePositiveBot|SupiBot)$"
```

##### Cleaned Messages - Shows messages removed by the Clean Chat filter.
```
message.content match r"(https?:\/\/|steam:\/\/)" || message.content match r"^(!|%|&|\*|`|~|;|m!|\\|/|@@)" || message.content match r"^\[.*] peepoTalk.*ImTalking" || flags.system_message || author.name match r"^(SchnozeBot|RibCrush|PhantomBot|Wizebot|Coebot|Moobot|Nightbot|StreamElements|Fossabot|ThePositiveBot|SupiBot)$"
```

##### Repetitive Spam - Shows messages removed by the NO Repetitive Spam filter.
```
message.content match r"(\b\S{2,}\b)(.*\b\1\b){4,}|^(?!.*https?:\/\/)(?!.*steam:\/\/)\S{35,}"
```

##### One Word Spam - Shows messages removed by the NO One Word Spam filter.
```
message.content match r"^(\S+)$"
```

# Regex example filters

### Standard chat message filter format: message.content match r"(word)"
#### ! = not (you don't want to see whats being filtered)
#### r = case sensitive
#### ri = not case sensitive
#### | = or
#### ^ = start of message
#### $ = end of message
#### .* = anything can be here

##### Remove messages containing word1 or word2.
```
!message.content match r"(word1|word2)"
```

##### Remove messages starting with word1 or word2.
```
!message.content match r"^(word1|word2)"
```

##### Remove messages ending with word1 or word2.
```
!message.content match r"(word1|word2)$"
```

##### Remove messages that are exactly word1 or word2.
```
!message.content match r"^(word1|word2)$"
```

##### Remove messages that start with word1, then some other words, then word2 with anything after that.
```
!message.content match r"^(word1.*word2)"
```

##### Show messages that contain word1 and word2 anywhere in the message, in any order.
```
message.content match r"^(?=.*word1)(?=.*word2)"
```
