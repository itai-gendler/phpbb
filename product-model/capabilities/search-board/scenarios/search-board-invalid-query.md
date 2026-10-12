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
      "text": "The query violates minimum/maximum/common-word or timing validation.",
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
      "text": "The query error is displayed without a successful search result.",
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

# Search board — invalid query

## Trigger

The query violates minimum/maximum/common-word or timing validation.

## Outcome

The query error is displayed without a successful search result.
