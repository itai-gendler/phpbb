---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User supplies the current password and entered replacement on Edit account settings.",
      "kind": "actor",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Username"
          ]
        }
      ],
      "contexts": {
        "community": {
          "place": "forum-web::community::account"
        }
      }
    },
    {
      "text": "The email change selects activation operator reactivation with email enabled and the registered identity is not privileged identity.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::account"
        }
      }
    },
    {
      "text": "Email is saved; the account becomes Inactive, activation operator activation is requested, current access ends and completion schedules the board.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Email",
            "Activation proof",
            "Inactivity reason"
          ],
          "to": "Inactive",
          "from": "Active"
        }
      ],
      "contexts": {
        "community": {
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

# Edit account settings — administrator reactivation

## Trigger

The email change selects administrator reactivation with email enabled and the account is not Founder.

## Outcome

Email is saved; the account becomes Inactive, administrator activation is requested, current access ends and completion schedules the board.
