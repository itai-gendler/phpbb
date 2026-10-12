---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits default posting choices with a valid form.",
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
      "text": "Posting defaults are saved for subsequent composing.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Posting defaults"
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

# Edit posting defaults — community

## Trigger

The account holder submits default posting choices with a valid form.

## Outcome

Posting defaults are saved for subsequent composing.
