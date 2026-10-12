---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens Manage saved entry.",
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
      "text": "Saved-list entries are disabled.",
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
      "text": "The saved entry process is unavailable and its list is not presented.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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
      "target": "phpBB/includes/ucp/ucp_main.php"
    }
  ]
}
---

# Browse bookmarks — bookmarks disabled

## Trigger

Bookmarks are disabled.

## Outcome

The bookmarks process is unavailable and its list is not presented.
