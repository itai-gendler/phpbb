---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows a valid stop-watching-discussion link.",
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
      "text": "The selected watch is removed and completion returns to the discussion.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "topic-subscription",
          "effect": "removes"
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

# Unsubscribe topic — community

## Trigger

The account holder follows a valid stop-watching-topic link.

## Outcome

The selected watch is removed and completion returns to the discussion.
