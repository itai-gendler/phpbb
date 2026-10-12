---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User confirms permanent deletion while other contributions remain.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The selected post and dependent files/reports are removed; summaries/counters are synchronized and completion schedules the remainder.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "post",
          "effect": "removes",
          "from": "Approved"
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
            "Approved count",
            "First post",
            "Last post",
            "Last contribution",
            "Attachments present",
            "Reported"
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
          "place": "forum-web::community::posting"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_posting.php#phpbb_handle_post_delete"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_admin.php#delete_posts"
    }
  ]
}
---

# Delete post permanently — community

## Trigger

The contributor confirms permanent deletion while other contributions remain.

## Outcome

The selected post and dependent files/reports are removed; summaries/counters are synchronized and completion schedules the remainder.
