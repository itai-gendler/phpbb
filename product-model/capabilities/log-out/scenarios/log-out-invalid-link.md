---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser",
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The signed-in person follows the supplied logout link.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::board-index"
        },
        "administration": {
          "place": "forum-web::administration"
        }
      }
    },
    {
      "text": "The supplied logout hash is invalid or the request has no signed-in identity.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::board-index"
        },
        "administration": {
          "place": "forum-web::administration"
        }
      }
    },
    {
      "text": "LOGOUT_FAILED is displayed; the requested signed-in logout is not completed.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::board-index"
        },
        "administration": {
          "place": "forum-web::administration"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/ucp.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions.php#login_box"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/auth/provider/db.php#login"
    }
  ]
}
---

# Log out — invalid link

## Trigger

The supplied logout hash is invalid or the request has no signed-in identity.

## Outcome

LOGOUT_FAILED is displayed; the requested signed-in logout is not completed.
