---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows the supplied remove-saved entry link.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::bookmarks"
        }
      }
    },
    {
      "text": "The registered identity holder selects saved entries in Manage saved entry and confirms removal.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::bookmarks"
        }
      }
    },
    {
      "text": "Only the selected registered identity entries are removed; completion remains in Manage bookmarks.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "bookmark",
          "effect": "removes"
        }
      ],
      "contexts": {
        "community": {
          "place": "forum-web::community::bookmarks"
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

# Remove topic bookmark — selected list removal

## Trigger

The account holder selects saved entries in Manage bookmarks and confirms removal.

## Outcome

Only the selected account entries are removed; completion remains in Manage bookmarks.
