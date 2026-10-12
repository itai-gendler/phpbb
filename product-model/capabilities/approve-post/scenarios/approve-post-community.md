---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator confirms approval of selected pending contributions.",
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
      "text": "Selected posts become Approved; summaries/counters and approval dispatch are maintained and the decision result is displayed.",
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

# Approve post — community

## Trigger

The moderator confirms approval of selected pending contributions.

## Outcome

Selected posts become Approved; summaries/counters and approval dispatch are maintained and the decision result is displayed.
