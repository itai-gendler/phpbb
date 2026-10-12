---
{
  "kind": "validation",
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
      "text": "Search configuration or entry policy sends the request to its refusal branch.",
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
      "text": "The configured disabled/refusal result is displayed without results.",
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

# Search board — disabled or denied

## Trigger

Search configuration or entry policy sends the request to its refusal branch.

## Outcome

The configured disabled/refusal result is displayed without results.
