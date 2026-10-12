---
{
  "kind": "edge",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits a supplied query and search options.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::search"
        },
        "community": {
          "place": "forum-web::community::search"
        }
      }
    },
    {
      "text": "The configured search module cannot be loaded.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::search"
        },
        "community": {
          "place": "forum-web::community::search"
        }
      }
    },
    {
      "text": "The search-module error is displayed; no search results are returned.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::search"
        },
        "community": {
          "place": "forum-web::community::search"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/search.php"
    }
  ]
}
---

# Search board — backend unavailable

## Trigger

The configured search module cannot be loaded.

## Outcome

The search-module error is displayed; no search results are returned.
