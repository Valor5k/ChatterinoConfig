##### Highlighted Only - Shows messages higlighlighted by your're Chatterino settings.
```
flags.highlighted
```

##### Sub Only - Shows messages sent by subscribers to the channel.
```
author.subbed
```

##### NO System Messages - Removes system messages such as subsciptions and timeouts, you will still see messages sent with subscriptions.
```
!flags.system_message
```

##### NO Bots - Removes bot accounts by there name. You can add bot accounts you see by adding their name divided by "|" (Case Sensitive).
```
!author.name match r"^(RibCrush|PhantomBot|Wizebot|Coebot|Moobot|Nightbot|StreamElements|Fossabot|ThePositiveBot|SupiBot)$"
```

##### NO Commands - Removes messages starting with common command characters such as "!uptime". Add or remove as you want, seperated by "|".
```
!message.content match r"^(!|#|\$|%|\^|&|\*|<|>|`|~|-|;|m!|\\|/|@@)"
```

##### NO Transcribing - Removes the spam transcribing the brodcaster in all languages.
```
!message.content match r"^\[.*] peepoTalk.*ImTalking"
```

##### Clean Chat - Combines NO System Messages, No Bots, No Commands, and NO Transcibinbg into one filter.
```
!author.name match r"^(RibCrush|PhantomBot|Wizebot|Coebot|Moobot|Nightbot|StreamElements|Fossabot|ThePositiveBot|SupiBot)$" && !message.content match r"^(!|#|\$|%|\^|&|\*|<|>|`|~|-|;|m!|\\|/|@@)" && !message.content match r"^\[.*] peepoTalk.*ImTalking" && !flags.system_message
```
