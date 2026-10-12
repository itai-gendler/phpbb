---
{
  "kind": "primary",
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
      "text": "The selected container is a redirecting container and tracking is enabled.",
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
      "text": "The Product consults posting area link Destination",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum-link",
          "effect": "reads",
          "facts": [
            "Destination"
          ]
        }
      ],
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
      "text": "The link's destination is followed and Redirect count is incremented; tracking disabled leaves the counter unchanged.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum-link",
          "effect": "changes",
          "facts": [
            "Redirect count"
          ]
        }
      ],
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

# Browse forums — link forum redirect

## Trigger

The selected container is a Forum link and tracking is enabled.

## Outcome

The link's destination is followed and Redirect count is incremented; tracking disabled leaves the counter unchanged.
