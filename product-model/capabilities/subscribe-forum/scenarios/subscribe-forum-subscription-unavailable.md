---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows a supplied watch-redirecting container.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::forum"
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
          "place": "forum-web::community::forum"
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
          "place": "forum-web::community::forum"
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

# Subscribe forum — subscription unavailable

## Trigger

The selected watch entry point reaches its unavailable branch.

## Outcome

No watch entry is added and the applicable unavailable result is displayed.
