---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows a valid watch-discussion link.",
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
      "text": "A discussion watch is stored for the registered identity and completion returns to the same discussion.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "topic-subscription",
          "effect": "creates",
          "facts": [
            "Owner",
            "Topic",
            "Notification status"
          ]
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

# Subscribe topic — community

## Trigger

The account holder follows a valid watch-topic link.

## Outcome

A topic watch is stored for the account and completion returns to the same discussion.
