---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator submits accepted member registration settings with a valid form.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::board-settings"
        }
      }
    },
    {
      "text": "Named registration/new-member/name/password/attempt/COPPA settings are saved.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "board-settings",
          "effect": "changes",
          "facts": [
            "Registration mode",
            "New member policy",
            "Name rules",
            "Password rules",
            "Forced password age",
            "Name change enabled",
            "Email reuse enabled",
            "Registration challenge",
            "Login attempt limit",
            "Registration attempt limit",
            "COPPA settings"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::administration::board-settings"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_board.php"
    }
  ]
}
---

# Change user registration settings — administration

## Trigger

The administrator submits accepted User registration settings with a valid form.

## Outcome

Named registration/new-member/name/password/attempt/COPPA settings are saved.
