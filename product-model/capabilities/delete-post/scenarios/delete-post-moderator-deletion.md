---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator confirms soft deletion of the selected contribution.",
      "kind": "actor",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The moderator confirms the selected posting deletion operation.",
      "kind": "condition",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The selected posting deletion and its synchronization complete through the moderator branch.",
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
        "community": {
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

# Delete post — moderator deletion

## Trigger

The moderator confirms the selected posting deletion operation.

## Outcome

The selected posting deletion and its synchronization complete through the moderator branch.
