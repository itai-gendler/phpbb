---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows the valid saved entry link on a selected discussion.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::topic"
        }
      }
    },
    {
      "text": "A bookmark is stored for the registered identity and discussion; completion returns to the same discussion.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "bookmark",
          "effect": "creates",
          "facts": [
            "Owner",
            "Topic"
          ]
        }
      ],
      "contexts": {
        "web": {
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

# Bookmark topic — community

## Trigger

The account holder follows the valid bookmark link on a selected topic.

## Outcome

A bookmark is stored for the account and topic; completion returns to the same discussion.
