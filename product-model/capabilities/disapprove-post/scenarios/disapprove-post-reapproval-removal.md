---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator selects a supplied reason and confirms queued disapproval.",
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
      "text": "The disapproval selection contains Reapproval required content.",
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
      "text": "Selected reapproval content is removed and applicable summaries and dispatch are maintained.",
      "kind": "product",
      "actor": "moderator",
      "entities": [
        {
          "entity": "post",
          "effect": "removes",
          "from": "Reapproval required"
        },
        {
          "entity": "attachment",
          "effect": "removes",
          "with": "post",
          "from": "Attached"
        },
        {
          "entity": "post-report",
          "effect": "removes",
          "with": "post",
          "from": "Open"
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Unapproved count",
            "Reported",
            "Attachments present",
            "First post",
            "Last post"
          ]
        },
        {
          "entity": "forum",
          "effect": "changes",
          "facts": [
            "Topic counts",
            "Last contribution"
          ]
        }
      ],
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

# Disapprove post — reapproval removal

## Trigger

The disapproval selection contains Reapproval required content.

## Outcome

Selected reapproval content is removed and applicable summaries and dispatch are maintained.
