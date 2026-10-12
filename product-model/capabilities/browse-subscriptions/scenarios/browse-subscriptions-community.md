---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens Manage subscriptions.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::subscriptions"
        }
      }
    },
    {
      "text": "The list displays this registered identity's topic/forum watches whose destinations survive filtering.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "topic-subscription",
          "effect": "reads",
          "facts": [
            "Owner",
            "Topic",
            "Notification status"
          ]
        },
        {
          "entity": "forum-subscription",
          "effect": "reads",
          "facts": [
            "Owner",
            "Forum",
            "Notification status"
          ]
        },
        {
          "entity": "topic",
          "effect": "reads",
          "facts": [
            "Subject",
            "Last contribution"
          ]
        },
        {
          "entity": "forum",
          "effect": "reads",
          "facts": [
            "Name",
            "Last contribution"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::subscriptions"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_main.php"
    }
  ]
}
---

# Browse subscriptions — community

## Trigger

The account holder opens Manage subscriptions.

## Outcome

The list displays this account's topic/forum watches whose destinations survive filtering.
