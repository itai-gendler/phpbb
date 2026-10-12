---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The signed-in person follows the valid logout link.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::board-index"
        }
      }
    },
    {
      "text": "Current signed-in access ends and completion schedules the board destination.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::board-index"
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

# Log out — community

## Trigger

The signed-in person follows the valid logout link.

## Outcome

Current signed-in access ends and completion schedules the board destination.
