---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows a supplied watch-discussion link.",
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
      "text": "The selected watch entry point reaches its unavailable branch.",
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
      "text": "No watch entry is added and the applicable unavailable result is displayed.",
      "kind": "product",
      "actor": "user",
      "entities": [],
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
      "target": "phpBB/includes/functions_display.php#watch_topic_forum"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_main.php"
    }
  ]
}
---

# Subscribe topic — subscription unavailable

## Trigger

The selected watch entry point reaches its unavailable branch.

## Outcome

No watch entry is added and the applicable unavailable result is displayed.
