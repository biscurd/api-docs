# Database structure

The folowing headings are the types used in the database.

## Member
| attribute | type           | size         | other info |
|-----------|----------------|--------------|------------|
| id | int | 2 bytes |
| token | int | 24 bytes |
| name | str["A-Z a-z 0-9 _ .",  6-bit per char] | 16 chars, 12 bytes | |
| display_name | str[unicode] | 24 bytes||
| email | str["a-z 0-9 @+.", 6-bit per char] | 40 char 30 bit | |
| pronouns | str["a-z", 5-bit per char] | 8 char | A slash will be added simular to the following CCCC/CCCC |
| about_me | str[unicode] | 64-bytes | |
| server | list[int 2-byte] | 40 server | |

## Bot
| attribute | type           | size         | other info |
|-----------|----------------|--------------|------------|
| id | int | 2 bytes |
| token | int | 24 bytes |
| name | str["A-Z a-z 0-9 _ .",  6-bit per char] | 16 chars, 12 bytes | |
| display_name | str[unicode] | 24 bytes||
| about_me | str[unicode] | 64 bytes | |

## Server
| attribute | type           | size         | other info |
|-----------|----------------|--------------|------------|
| id | int | 2 bytes |
| name | str["A-Z a-z 0-9 _ .",  6-bit per char] | 16 chars, 12 bytes | |
| display_name | str[unicode] | 24 bytes||
| channels | list[Channel 2-byte per channel] | 40 server  | |
| channel_categories | list[ChannelCategory 2-byte per ChannelCategory] | 40 channel  | |
| member | list[int 2-byte] | 40 server | |

## ChannelCategory
| attribute | type           | size         | other info |
|-----------|----------------|--------------|------------|
| id | int | 2 bytes |
| display_name | str[unicode] | 24 bytes||
| channels | list[Channel 2-byte per channel] | 40 channel | |

## Channel
| attribute | type           | size         | other info |
|-----------|----------------|--------------|------------|
| id | int | 2 bytes |
| display_name | str[unicode] | 24 bytes||
| messages | list[Message 4-byte per message] | 1024 messages | |

## Message
| attribute | type           | size         | other info |
|-----------|----------------|--------------|------------|
| id | int | 4 bytes |
| reaction | str[unicode] | 6 bytes||
| content | str[unicode] | 256 bytes max |  |

## Reaction
| attribute | type           | size         | other info |
|-----------|----------------|--------------|------------|
| id | int | 2 bytes |
| emoji | str[unicode] | 4 bytes| |

# Other
- Members and bots also have an profile picture attribute
- Server also have an banner attribute
