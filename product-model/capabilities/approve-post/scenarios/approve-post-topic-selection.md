---
{
  "kind": "primary",
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
      "text": "The moderator confirms a pending-discussion selection.",
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
      "text": "The selected topic and its applicable pending posts become Approved, counts/first/last are synchronized and approval dispatch runs.",
      "kind": "product",
      "actor": "moderator",
      "entities": [
        {
          "entity": "post",
          "effect": "changes",
          "facts": [
            "Visibility"
          ],
          "from": "Unapproved",
          "to": "Approved"
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Visibility",
            "Approved count",
            "Unapproved count",
            "First post",
            "Last post",
            "Last contribution"
          ],
          "from": "Unapproved",
          "to": "Approved"
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

# Approve post — topic selection

## Trigger

The moderator confirms a pending-topic selection.

## Outcome

The selected topic and its applicable pending posts become Approved, counts/first/last are synchronized and approval dispatch runs.
