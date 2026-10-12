---
{
  "entities": [
    {
      "entity": "topic-subscription",
      "shows": [
        "Owner",
        "Topic",
        "Notification status"
      ]
    },
    {
      "entity": "forum-subscription",
      "shows": [
        "Owner",
        "Forum",
        "Notification status"
      ]
    },
    {
      "entity": "topic",
      "shows": [
        "Subject",
        "Last contribution"
      ]
    },
    {
      "entity": "forum",
      "shows": [
        "Name",
        "Last contribution"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_main.php"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "ucp.php?i=main&mode=subscribed"
    }
  ]
}
---

# Subscriptions

The working context for subscriptions. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
