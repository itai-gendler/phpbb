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
      "text": "Confirmed disapproval removes all selected discussion content.",
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
      "text": "The topic and applicable posts/dependents are removed, summaries synchronized and the disapproval result displayed.",
      "kind": "product",
      "actor": "moderator",
      "entities": [
        {
          "entity": "topic",
          "effect": "removes",
          "from": "Unapproved"
        },
        {
          "entity": "post",
          "effect": "removes",
          "with": "topic",
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
          "entity": "bookmark",
          "effect": "removes",
          "with": "topic"
        },
        {
          "entity": "topic-subscription",
          "effect": "removes",
          "with": "topic"
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

# Disapprove post — whole topic removal

## Trigger

Confirmed disapproval removes all selected topic content.

## Outcome

The topic and applicable posts/dependents are removed, summaries synchronized and the disapproval result displayed.
