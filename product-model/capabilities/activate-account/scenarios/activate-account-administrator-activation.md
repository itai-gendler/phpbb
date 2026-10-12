---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The Administrator follows the self-activation link with the entered registered identity and key.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::activation"
        }
      }
    },
    {
      "text": "The administrator submits matching activation information for an eligible inactive registered identity.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::activation"
        }
      }
    },
    {
      "text": "The selected account becomes Active and the applicable activation log/welcome dispatch and completion occur.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Inactivity reason",
            "Activation proof",
            "Reset proof",
            "Reset expiry"
          ],
          "from": "Inactive",
          "to": "Active"
        }
      ],
      "contexts": {
        "community": {
          "place": "forum-web::community::activation"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_activate.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_user.php#user_active_flip"
    }
  ]
}
---

# Activate account — administrator activation

## Trigger

The administrator submits matching activation information for an eligible inactive account.

## Outcome

The selected account becomes Active and the applicable activation log/welcome dispatch and completion occur.
