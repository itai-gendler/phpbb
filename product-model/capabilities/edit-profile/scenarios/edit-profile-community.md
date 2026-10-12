---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits valid profile values and applicable birthday input.",
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
      "text": "The profile values and applicable birthday are saved.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Profile values",
            "Birthday"
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
      "target": "phpBB/includes/ucp/ucp_profile.php"
    }
  ]
}
---

# Edit profile — community

## Trigger

The account holder submits valid profile values and applicable birthday input.

## Outcome

The profile values and applicable birthday are saved.
