# Sample messages

## Photo message

Sanitized from a [captured Telegram webhook](https://gist.github.com/otnansirk/759ef10ad21aa889810c8af7cbcd03bc).

```json
{
  "update_id": 312744884,
  "message": {
    "message_id": 17,
    "from": {
      "id": 100000001,
      "is_bot": false,
      "first_name": "Test User",
      "username": "testuser",
      "language_code": "en"
    },
    "chat": {
      "id": 100000001,
      "first_name": "Test User",
      "username": "testuser",
      "type": "private"
    },
    "date": 1753164384,
    "photo": [
      {
        "file_id": "AgACAgUAAxkBAAMRaH8qXw-VQSGAG4X4VoCg9A5nE50AAvLGMRtBGPlXGt4-FX4l2_oBAAMCAANzAAM2BA",
        "file_unique_id": "AQAD8sYxG0EY-Vd4",
        "file_size": 1705,
        "width": 72,
        "height": 90
      },
      {
        "file_id": "AgACAgUAAxkBAAMRaH8qXw-VQSGAG4X4VoCg9A5nE50AAvLGMRtBGPlXGt4-FX4l2_oBAAMCAANtAAM2BA",
        "file_unique_id": "AQAD8sYxG0EY-Vdy",
        "file_size": 32527,
        "width": 255,
        "height": 320
      },
      {
        "file_id": "AgACAgUAAxkBAAMRaH8qXw-VQSGAG4X4VoCg9A5nE50AAvLGMRtBGPlXGt4-FX4l2_oBAAMCAAN4AAM2BA",
        "file_unique_id": "AQAD8sYxG0EY-Vd9",
        "file_size": 137906,
        "width": 638,
        "height": 800
      },
      {
        "file_id": "AgACAgUAAxkBAAMRaH8qXw-VQSGAG4X4VoCg9A5nE50AAvLGMRtBGPlXGt4-FX4l2_oBAAMCAAN5AAM2BA",
        "file_unique_id": "AQAD8sYxG0EY-Vd-",
        "file_size": 173215,
        "width": 816,
        "height": 1023
      }
    ]
  }
}
```

## Sticker message

Sanitized sticker update, shape per the
[Bot API `Sticker` object](https://core.telegram.org/bots/api#sticker). The
message carries no `text`; `emoji` and `set_name` are both optional, so a
parser must not rely on either. A still sticker is WebP; `is_video` marks a
WebM one and `is_animated` a Lottie (TGS) one.

```json
{
  "update_id": 312744887,
  "message": {
    "message_id": 321,
    "from": {
      "id": 100000001,
      "is_bot": false,
      "first_name": "Test User",
      "username": "testuser",
      "language_code": "en"
    },
    "chat": {
      "id": 100000001,
      "first_name": "Test User",
      "username": "testuser",
      "type": "private"
    },
    "date": 1756290120,
    "sticker": {
      "file_id": "CAACAgIAAxkBAAIBQWjPMV5rZ0dEUvO0kQABt3l0aFYyAAJKAANZu_wlnFJ1RE9WuJk2BA",
      "file_unique_id": "AgADSgADWbv8JQ",
      "type": "regular",
      "width": 512,
      "height": 512,
      "is_animated": false,
      "is_video": false,
      "emoji": "😀",
      "set_name": "TestPack",
      "thumbnail": {
        "file_id": "AAMCAgADGQEAAgFBaM8xXmtnR0RS87SRAAG3eXRoVjIAAkoAA1m7_CWcUnVET1a4mQEAB20AAzYE",
        "file_unique_id": "AQADSgADWbv8JXI",
        "file_size": 5304,
        "width": 128,
        "height": 128
      },
      "file_size": 36042
    }
  }
}
```

## Animation (GIF) message

Sanitized animation update, shape per the
[Bot API `Message.animation` field](https://core.telegram.org/bots/api#message):
"For backward compatibility, when this field is set, the *document* field will
also be set." Both fields describe the same file (same `file_id`), so a parser
that walks both produces a duplicate attachment.

```json
{
  "update_id": 312744888,
  "message": {
    "message_id": 322,
    "from": {
      "id": 100000001,
      "is_bot": false,
      "first_name": "Test User",
      "username": "testuser",
      "language_code": "en"
    },
    "chat": {
      "id": 100000001,
      "first_name": "Test User",
      "username": "testuser",
      "type": "private"
    },
    "date": 1756290180,
    "animation": {
      "file_id": "CgACAgQAAxkBAAIBQmjPMbXhH2m0T3nQAAFrJ8x0aFYyAAK0AgACWbv8U5FQn0lmQnUsNgQ",
      "file_unique_id": "AgADtAIAAlm7_FM",
      "file_name": "cat.mp4",
      "mime_type": "video/mp4",
      "duration": 3,
      "width": 480,
      "height": 480,
      "thumbnail": {
        "file_id": "AAMCBAADGQEAAgFCaM8xteEfabRPedAAAWsnzHRoVjIAArQCAAJZu_xTkVCfSWZCdSwBAAdtAAM2BA",
        "file_unique_id": "AQADtAIAAlm7_FNy",
        "file_size": 12816,
        "width": 320,
        "height": 320
      },
      "file_size": 291345
    },
    "document": {
      "file_id": "CgACAgQAAxkBAAIBQmjPMbXhH2m0T3nQAAFrJ8x0aFYyAAK0AgACWbv8U5FQn0lmQnUsNgQ",
      "file_unique_id": "AgADtAIAAlm7_FM",
      "file_name": "cat.mp4",
      "mime_type": "video/mp4",
      "thumbnail": {
        "file_id": "AAMCBAADGQEAAgFCaM8xteEfabRPedAAAWsnzHRoVjIAArQCAAJZu_xTkVCfSWZCdSwBAAdtAAM2BA",
        "file_unique_id": "AQADtAIAAlm7_FNy",
        "file_size": 12816,
        "width": 320,
        "height": 320
      },
      "file_size": 291345
    }
  }
}
```

## Reply to a bot message in a group

Sanitized from a captured webhook: a user replies to one of the bot's own
messages in a supergroup. `reply_to_message.from` is the bot account. With
`mentionOnReply` enabled this counts as a mention.

```json
{
  "update_id": 312744885,
  "message": {
    "message_id": 108,
    "from": {
      "id": 100000001,
      "is_bot": false,
      "first_name": "Test User",
      "username": "testuser",
      "language_code": "en"
    },
    "chat": {
      "id": -1001000000001,
      "title": "Test Group",
      "type": "supergroup"
    },
    "date": 1756290000,
    "reply_to_message": {
      "message_id": 105,
      "from": {
        "id": 8000000001,
        "is_bot": true,
        "first_name": "Test Bot",
        "username": "testbot"
      },
      "chat": {
        "id": -1001000000001,
        "title": "Test Group",
        "type": "supergroup"
      },
      "date": 1756289940,
      "text": "The first option is usually the safer choice."
    },
    "text": "and the second one?"
  }
}
```

## Forum topic message with an implicit reply

Sanitized from a captured webhook in a forum supergroup. Every message posted
inside a topic carries `reply_to_message` pointing at the topic-creation
service message, whose `message_id` equals `message_thread_id` and whose
`from` is whoever created the topic (the bot, when it called
`createForumTopic`). This is not an explicit reply and must not count as a
mention under `mentionOnReply`.

```json
{
  "update_id": 312744886,
  "message": {
    "message_id": 214,
    "from": {
      "id": 100000001,
      "is_bot": false,
      "first_name": "Test User",
      "username": "testuser",
      "language_code": "en"
    },
    "chat": {
      "id": -1001000000002,
      "title": "Test Forum",
      "type": "supergroup",
      "is_forum": true
    },
    "date": 1756290060,
    "message_thread_id": 200,
    "is_topic_message": true,
    "reply_to_message": {
      "message_id": 200,
      "from": {
        "id": 8000000001,
        "is_bot": true,
        "first_name": "Test Bot",
        "username": "testbot"
      },
      "chat": {
        "id": -1001000000002,
        "title": "Test Forum",
        "type": "supergroup",
        "is_forum": true
      },
      "date": 1756289000,
      "message_thread_id": 200,
      "is_topic_message": true,
      "forum_topic_created": {
        "name": "Support",
        "icon_color": 7322096
      }
    },
    "text": "does anyone know how to configure this?"
  }
}
```
