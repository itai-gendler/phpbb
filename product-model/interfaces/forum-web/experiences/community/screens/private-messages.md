---
{
  "entities": [
    {
      "entity": "private-message",
      "shows": [
        "Subject",
        "Sender",
        "Sent at"
      ]
    },
    {
      "entity": "message-copy",
      "shows": [
        "Owner",
        "Message",
        "Folder",
        "New",
        "Unread",
        "Deleted"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_pm.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_pm_compose.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#submit_pm"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "ucp.php?i=pm&mode=view"
    }
  ]
}
---

# Private messages

The working context for private messages. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
