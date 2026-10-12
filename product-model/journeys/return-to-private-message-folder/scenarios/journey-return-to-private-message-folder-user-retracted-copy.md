---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The User opens the selected retracted mailbox item.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-message"
        }
      },
      "capability": "view-private-message"
    },
    {
      "text": "The selected copy is absent or its shared content is flagged deleted/retracted.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-message"
        }
      },
      "capability": "view-private-message"
    },
    {
      "text": "The missing/deleted result is displayed; the deleted-copy branch schedules its folder rather than exposing removed content.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-message"
        }
      },
      "capability": "view-private-message"
    },
    {
      "text": "The Product carries User through the completion destination into browse shared message",
      "kind": "product",
      "actor": "user",
      "capability": "view-private-message",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-message"
        }
      }
    },
    {
      "text": "The User opens a supported mailbox folder.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-messages"
        }
      },
      "capability": "browse-private-messages"
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
      },
      "capability": "browse-private-messages"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#delete_pm"
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
      "target": "phpBB/includes/ucp/ucp_pm_viewmessage.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#update_unread_status"
    }
  ]
}
---

# Return to private message folder — user retracted copy

## Trigger

Reach the folder after copy removal or deleted-content handling.

## Outcome

The same account holder reaches a mailbox list through the scheduled folder destination.
