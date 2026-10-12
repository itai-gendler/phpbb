---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator selects a valid reason and confirms queued disapproval.",
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
      "text": "Selected posts and dependent records are removed; summaries and applicable reason-bearing board alert dispatch are maintained.",
      "kind": "product",
      "actor": "moderator",
      "entities": [
        {
          "entity": "post",
          "effect": "removes",
          "from": "Unapproved"
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

# Disapprove post — community

## Trigger

The moderator selects a valid reason and confirms queued disapproval.

## Outcome

Selected posts and dependent records are removed; summaries and applicable reason-bearing notification dispatch are maintained.
