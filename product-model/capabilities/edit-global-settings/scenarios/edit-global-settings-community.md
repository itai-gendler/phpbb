---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits valid personal global preferences.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::account"
        }
      }
    },
    {
      "text": "Language, timezone, date format, accepted style, contact preferences and applicable online visibility are saved.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Preferred language",
            "Timezone",
            "Date format",
            "Style",
            "Allow private messages",
            "Allow email contact",
            "Allow mass email",
            "Online visibility"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::account"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_prefs.php"
    }
  ]
}
---

# Edit global settings — community

## Trigger

The account holder submits valid personal global preferences.

## Outcome

Language, timezone, date format, accepted style, contact preferences and applicable online visibility are saved.
