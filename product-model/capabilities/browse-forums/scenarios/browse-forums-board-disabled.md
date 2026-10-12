---
{
  "kind": "validation",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens the board index.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::board-index"
        },
        "community": {
          "place": "forum-web::community::board-index"
        }
      }
    },
    {
      "text": "The board availability/load gate intercepts this request.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::board-index"
        },
        "community": {
          "place": "forum-web::community::board-index"
        }
      }
    },
    {
      "text": "The configured unavailable-board result is displayed rather than the hierarchy.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::board-index"
        },
        "community": {
          "place": "forum-web::community::board-index"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/index.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewforum.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_display.php#display_forums"
    }
  ]
}
---

# Browse forums — board disabled

## Trigger

The board availability/load gate intercepts this request.

## Outcome

The configured unavailable-board result is displayed rather than the hierarchy.
