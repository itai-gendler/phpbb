---
{
  "entities": [
    {
      "entity": "private-message",
      "shows": [
        "Subject",
        "Content",
        "Sender",
        "To recipients",
        "Blind-copy recipients",
        "Sent at",
        "Formatting choices",
        "Edit information"
      ],
      "collects": [
        "Subject",
        "Content",
        "To recipients",
        "Blind-copy recipients",
        "Formatting choices"
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
    },
    {
      "entity": "attachment",
      "shows": [
        "Filename",
        "Comment",
        "Size",
        "Media classification",
        "File content",
        "Binding"
      ],
      "collects": [
        "File content",
        "Filename",
        "Comment"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_pm_viewmessage.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#update_unread_status"
    },
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#delete_pm"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "ucp.php?i=pm&mode=compose"
    }
  ]
}
---

# Private message

The working context for private message. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers. Address display filters each blind individual/group through the sender, self and membership policy.
