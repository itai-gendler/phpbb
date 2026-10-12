---
{
  "kind": "primary",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows the self-activation link with the entered registered identity and key.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::activation"
        },
        "community": {
          "place": "forum-web::community::activation"
        }
      }
    },
    {
      "text": "The registered identity is already Active without an applicable pending password reminder.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::activation"
        },
        "community": {
          "place": "forum-web::community::activation"
        }
      }
    },
    {
      "text": "The already-activated result is displayed without another activation change.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::activation"
        },
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

# Activate account — already active

## Trigger

The account is already Active without an applicable pending password reminder.

## Outcome

The already-activated result is displayed without another activation change.
