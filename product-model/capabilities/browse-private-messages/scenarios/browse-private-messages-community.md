---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens a supported mailbox folder.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-messages"
        }
      }
    },
    {
      "text": "The folder displays this registered identity's copies and disclosed message summaries.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "message-copy",
          "effect": "reads",
          "facts": [
            "Owner",
            "Message",
            "Folder",
            "New",
            "Unread",
            "Deleted"
          ]
        },
        {
          "entity": "private-message",
          "effect": "reads",
          "facts": [
            "Subject",
            "Sender",
            "Sent at"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-messages"
        }
      }
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
  ]
}
---

# Browse private messages — community

## Trigger

The account holder opens a supported mailbox folder.

## Outcome

The folder displays this account's copies and disclosed message summaries.
