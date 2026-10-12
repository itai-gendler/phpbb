---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "creates",
      "contexts": [
        {
          "place": "forum-web::public::registration"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "entity": "board-settings",
          "fact": "Registration mode",
          "is": "No activation (immediate access)"
        }
      ]
    },
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "entity": "board-settings",
          "fact": "Registration mode",
          "is": "By user (email verification)"
        },
        {
          "entity": "board-settings",
          "fact": "Email enabled",
          "is": true
        }
      ]
    },
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "entity": "board-settings",
          "fact": "Registration mode",
          "is": "By admin"
        },
        {
          "entity": "board-settings",
          "fact": "Email enabled",
          "is": true
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_register.php"
    }
  ]
}
---

# Account registration requires the configured operation authority

Pre-authentication User; configured registration availability, including disabled/email-dependent modes.
