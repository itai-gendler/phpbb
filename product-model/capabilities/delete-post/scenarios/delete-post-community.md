---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User confirms soft deletion of the selected contribution.",
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
      "text": "The retained post becomes Deleted, deletion information and summaries/counters are synchronized, and completion schedules the remainder.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "post",
          "effect": "changes",
          "facts": [
            "Visibility",
            "Deletion information"
          ],
          "from": "Approved",
          "to": "Deleted"
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Approved count",
            "Deleted count",
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

# Delete post — community

## Trigger

The contributor confirms soft deletion of the selected post.

## Outcome

The retained post becomes Deleted, deletion information and summaries/counters are synchronized, and completion schedules the remainder.
