##### Highlighted Only
```
flags.highlighted
```

##### Sub Only
```
author.subbed
```

##### NO System Messages
```
!flags.system_message
```

##### NO Bots
```
!author.name match r"^(RibCrush|PhantomBot|Wizebot|Coebot|Moobot|Nightbot|StreamElements|Fossabot|ThePositiveBot|SupiBot)$"
```

##### NO Commands
```
!message.content match r"^(!|#|\$|%|\^|&|\*|<|>|`|~|-|;|m!|\\|/|@@)"
```

##### NO Transcribing
```
!message.content match r"^\[.*] peepoTalk.*ImTalking"
```

##### Clean Chat
```
!author.name match r"^(RibCrush|PhantomBot|Wizebot|Coebot|Moobot|Nightbot|StreamElements|Fossabot|ThePositiveBot|SupiBot)$" && !message.content match r"^(!|#|\$|%|\^|&|\*|<|>|`|~|-|;|m!|\\|/|@@)" && !message.content match r"^\[.*] peepoTalk.*ImTalking" && !flags.system_message
```
