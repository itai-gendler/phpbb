---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The User confirms ordinary-folder copy removal while other copies remain.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-message"
        }
      },
      "capability": "delete-private-message"
    },
    {
      "text": "Only that copy is removed, counters are maintained and completion schedules its folder.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "message-copy",
          "effect": "removes",
          "from": "Available"
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "New message count",
            "Unread message count"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-message"
        }
      },
      "capability": "delete-private-message"
    },
    {
      "text": "The Product carries User through the completion destination into browse shared message",
      "kind": "product",
      "actor": "user",
      "capability": "delete-private-message",
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

# Return to private message folder — user delete

## Trigger

Reach the folder after copy removal or deleted-content handling.

## Outcome

The same account holder reaches a mailbox list through the scheduled folder destination.
