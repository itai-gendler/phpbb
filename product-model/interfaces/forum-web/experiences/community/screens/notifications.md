---
{
  "entities": [
    {
      "entity": "notification",
      "shows": [
        "Event",
        "Origin",
        "Destination",
        "Created at",
        "Read status",
        "Display information"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_notifications.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/notification/method/board.php"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "ucp.php?i=ucp_notifications&mode=notification_list"
    }
  ]
}
---

# Notifications

The working context for notifications. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
