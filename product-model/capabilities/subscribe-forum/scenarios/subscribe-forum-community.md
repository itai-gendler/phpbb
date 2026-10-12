---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows a valid watch-redirecting container.",
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
      "text": "A posting area watch is stored for the registered identity and completion returns to the same posting area.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum-subscription",
          "effect": "creates",
          "facts": [
            "Owner",
            "Forum",
            "Notification status"
          ]
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

# Subscribe forum — community

## Trigger

The account holder follows a valid watch-forum link.

## Outcome

A forum watch is stored for the account and completion returns to the same forum.
