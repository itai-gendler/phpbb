---
{
  "kind": "validation",
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
      "text": "The selected registered identity/key combination is missing, mismatched or manually inactive.",
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
      "text": "The invalid activation result is displayed; the target is not activated.",
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

# Activate account — invalid key

## Trigger

The selected account/key combination is missing, mismatched or manually inactive.

## Outcome

The invalid activation result is displayed; the target is not activated.
