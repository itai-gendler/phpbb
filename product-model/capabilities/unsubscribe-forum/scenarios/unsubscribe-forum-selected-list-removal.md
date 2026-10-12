---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User follows a supplied stop-watching-redirecting container.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::subscriptions"
        }
      }
    },
    {
      "text": "The registered identity holder selects watches in Manage subscriptions and submits removal.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::subscriptions"
        }
      }
    },
    {
      "text": "Selected registered identity watches are removed even when the board alert switch no longer offers subscription creation; completion remains in the saved list.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "forum-subscription",
          "effect": "removes"
        }
      ],
      "contexts": {
        "community": {
          "place": "forum-web::community::subscriptions"
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

# Unsubscribe forum — selected list removal

## Trigger

The account holder selects watches in Manage subscriptions and submits removal.

## Outcome

Selected account watches are removed even when the notification switch no longer offers subscription creation; completion remains in the saved list.
