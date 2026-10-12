---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows the valid remove-saved entry link.",
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
      "text": "The registered identity's selected bookmark is removed and completion returns to the discussion.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "bookmark",
          "effect": "removes"
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

# Remove topic bookmark — community

## Trigger

The account holder follows the valid remove-bookmark link.

## Outcome

The account's selected bookmark is removed and completion returns to the discussion.
