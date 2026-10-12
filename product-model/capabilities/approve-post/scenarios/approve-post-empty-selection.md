---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator confirms approval of selected pending contributions.",
      "kind": "actor",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::post-review"
        }
      }
    },
    {
      "text": "The submitted selection has no existing/admitted entries.",
      "kind": "condition",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::post-review"
        }
      }
    },
    {
      "text": "The empty-selection result is displayed without an approval change.",
      "kind": "product",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::post-review"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/mcp/mcp_queue.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_mcp.php#phpbb_check_ids"
    }
  ]
}
---

# Approve post — empty selection

## Trigger

The submitted selection has no existing/admitted entries.

## Outcome

The empty-selection result is displayed without an approval change.
