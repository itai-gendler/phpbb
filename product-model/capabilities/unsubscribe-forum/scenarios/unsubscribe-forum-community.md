---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows a valid stop-watching-redirecting container.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::forum"
        }
      }
    },
    {
      "text": "The selected watch is removed and completion returns to the posting area.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum-subscription",
          "effect": "removes"
        }
      ],
      "contexts": {
        "web": {
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

# Unsubscribe forum — community

## Trigger

The account holder follows a valid stop-watching-forum link.

## Outcome

The selected watch is removed and completion returns to the forum.
