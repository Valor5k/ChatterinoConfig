##### Highlighted Only - Shows messages highlighted by your Chatterino settings.
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

##### NO Bots - Removes bot accounts by their name. You can add bot accounts you see by adding their name seperated by "|" (Case Sensitive).
```
!author.name match r"^(PhantomBot|Wizebot|Coebot|Moobot|Nightbot|StreamElements|Fossabot|ThePositiveBot|SupiBot|RibCrush)$"
```

##### NO Commands - Removes messages starting with common command characters such as "!uptime". Add or remove as you want, seperated by "|". These characters: + . * ? ^ $ ( ) [ ] { } | \ are special and must be preceded by "\\" eg. "\\$" = "$".
```
!message.content match r"^(!|#|\$|%|\^|&|\*|<|>|`|~|-|;|m!|\\|/|@@)"
```

##### NO Transcribing - Removes the spam transcribing the brodcaster in all languages.
```
!message.content match r"^\[.*] peepoTalk.*ImTalking"
```

##### Clean Chat - Combines NO System Messages, No Bots, No Commands, and NO Transcibinbg into one filter.
```
!author.name match r"^(PhantomBot|Wizebot|Coebot|Moobot|Nightbot|StreamElements|Fossabot|ThePositiveBot|SupiBot|RibCrush)$" && !message.content match r"^(!|#|\$|%|\^|&|\*|<|>|`|~|-|;|m!|\\|/|@@)" && !message.content match r"^\[.*] peepoTalk.*ImTalking" && !flags.system_message
```

##### Filters.json - This can be pasted over the existing "filtering" section of your settings file at C:\Users\\"username"\AppData\Roaming\Chatterino2\Settings to get all the above filters in one go.
```
"filtering": {
        "filters": [
            {
                "name": "Highlighted",
                "filter": "flags.highlighted",
                "id": "ffba0b54-2066-4f69-adce-7a4cd910beb8"
            },
            {
                "name": "Sub Only",
                "filter": "author.subbed",
                "id": "d1ad8b6f-860d-45c4-bb89-ed8be3d4c902"
            },
            {
                "name": "Clean Chat",
                "filter": "!author.name match r\"^(PhantomBot|Wizebot|Coebot|Moobot|Nightbot|StreamElements|Fossabot|ThePositiveBot|SupiBot|RibCrush)$\" && !message.content match r\"^(!|#|\\$|%|\\^|&|\\*|<|>|`|~|-|;|m!|\\\\|/|@@)\" && !message.content match r\"^\\[.*] peepoTalk.*ImTalking\" && !flags.system_message",
                "id": "30c55051-430f-4ef0-a543-edd3b5e45d32"
            },
            {
                "name": "NO Bots",
                "filter": "!author.name match r\"^(PhantomBot|Wizebot|Coebot|Moobot|Nightbot|StreamElements|Fossabot|ThePositiveBot|SupiBot|RibCrush)$\"",
                "id": "1b184b48-fef5-44b6-bea1-00116f16b00b"
            },
            {
                "name": "NO Commands",
                "filter": "!message.content match r\"^(!|#|\\$|%|\\^|&|\\*|<|>|`|~|-|;|m!|\\\\|/|@@)\"",
                "id": "366cf514-3a92-430a-9f74-39a43ca386cc"
            },
            {
                "name": "NO Transcribing",
                "filter": "!message.content match r\"^\\[.*] peepoTalk.*ImTalking\"",
                "id": "51058dae-3756-4a24-b5d3-04b459fdcf66"
            },
            {
                "name": "NO System Messages",
                "filter": "!flags.system_message",
                "id": "7ffffbac-cb3e-4633-b616-ee341511e0b8"
            },
        ],
        "excludeUserMessages": true
    },
```
