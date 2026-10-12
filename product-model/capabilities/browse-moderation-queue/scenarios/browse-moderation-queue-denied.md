---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator opens the pending-discussion or pending-contribution queue.",
      "kind": "actor",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::moderation-queue"
        }
      }
    },
    {
      "text": "The queue request reaches its entry/refusal branch.",
      "kind": "condition",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::moderation-queue"
        }
      }
    },
    {
      "text": "The queue content is not disclosed.",
      "kind": "product",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::moderation-queue"
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

# Browse moderation queue — denied

## Trigger

The queue request reaches its entry/refusal branch.

## Outcome

The queue content is not disclosed.
