---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator opens the pending-discussion or pending-contribution queue.",
      "kind": "actor",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::moderation-queue"
        }
      }
    },
    {
      "text": "The selected section displays its filtered pending contributions or empty result.",
      "kind": "product",
      "actor": "moderator",
      "entities": [
        {
          "entity": "topic",
          "effect": "reads",
          "facts": [
            "Subject",
            "Author",
            "Visibility"
          ]
        },
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Subject",
            "Author",
            "Posted at",
            "Visibility"
          ]
        }
      ],
      "contexts": {
        "web": {
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

# Browse moderation queue — community

## Trigger

The moderator opens the pending-topic or pending-post queue.

## Outcome

The selected section displays its filtered pending contributions or empty result.
