---
{
  "kind": "primary",
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
      "text": "The watch request lacks the valid shortcut hash but can enter confirmation.",
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
      "text": "The Product asks for confirmation; confirming with the valid process adds the watch and returns to its destination.",
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

# Subscribe topic — confirmation required

## Trigger

The watch request lacks the valid shortcut hash but can enter confirmation.

## Outcome

The Product asks for confirmation; confirming with the valid process adds the watch and returns to its destination.
