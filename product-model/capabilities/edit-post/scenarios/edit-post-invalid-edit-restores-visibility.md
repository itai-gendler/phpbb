---
{
  "kind": "edge",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator submits proposed edits to the selected contribution.",
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
      "text": "The selected contribution is Deleted and the early restoration branch runs before accumulated final validation errors are handled.",
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
      "text": "The post becomes Approved and visibility summaries are synchronized even though the editor later displays its form/content error and does not save the proposed text.",
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
          "to": "Approved",
          "from": "Deleted"
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
      "target": "phpBB/posting.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_posting.php#submit_post"
    }
  ]
}
---

# Edit post — invalid edit restores visibility

## Trigger

The selected post is Deleted and the early restoration branch runs before accumulated final validation errors are handled.

## Outcome

The post becomes Approved and visibility summaries are synchronized even though the editor later displays its form/content error and does not save the proposed text.
