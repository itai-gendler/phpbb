---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens an approved discussion.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::topic"
        }
      }
    },
    {
      "text": "Own pending visibility is enabled and the signed-in author selects their Unapproved or Reapproval required contribution.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::topic"
        }
      }
    },
    {
      "text": "The author's admitted pending contribution is displayed; Deleted content gains no ordinary-author exception.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "topic",
          "effect": "reads",
          "facts": [
            "Subject",
            "Visibility"
          ]
        },
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Author",
            "Visibility",
            "Formatting choices"
          ]
        }
      ],
      "contexts": {
        "community": {
          "place": "forum-web::community::topic"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewtopic.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php#is_visible"
    }
  ]
}
---

# Read topic — own pending post

## Trigger

Own pending visibility is enabled and the signed-in author selects their Unapproved or Reapproval required contribution.

## Outcome

The author's admitted pending contribution is displayed; Deleted content gains no ordinary-author exception.
