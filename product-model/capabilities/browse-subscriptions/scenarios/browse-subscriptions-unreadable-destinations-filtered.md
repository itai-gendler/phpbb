---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens Manage subscriptions.",
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
      "text": "Some watched posting area/discussion are excluded by destination filtering.",
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
      "text": "Excluded destinations are absent from the displayed list; this is not automatic deletion of all watches.",
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
      "target": "phpBB/includes/ucp/ucp_main.php"
    }
  ]
}
---

# Browse subscriptions — unreadable destinations filtered

## Trigger

Some watched forums/topics are excluded by destination filtering.

## Outcome

Excluded destinations are absent from the displayed list; this is not automatic deletion of all watches.
