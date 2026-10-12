---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator confirms restoration of selected deleted contributions.",
      "kind": "actor",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::post-review"
        }
      }
    },
    {
      "text": "Selected posts become Approved; visibility, summaries/counters and the distinct restoration dispatch path are maintained.",
      "kind": "product",
      "actor": "moderator",
      "entities": [
        {
          "entity": "post",
          "effect": "changes",
          "facts": [
            "Visibility",
            "Deletion information"
          ],
          "from": "Deleted",
          "to": "Approved"
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Visibility",
            "Approved count",
            "Deleted count",
            "Last contribution"
          ]
        },
        {
          "entity": "forum",
          "effect": "changes",
          "facts": [
            "Topic counts",
            "Last contribution"
          ]
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Post count"
          ]
        }
      ],
      "contexts": {
        "web": {
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

# Restore post — community

## Trigger

The moderator confirms restoration of selected deleted contributions.

## Outcome

Selected posts become Approved; visibility, summaries/counters and the distinct restoration dispatch path are maintained.
