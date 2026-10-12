---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The User follows a supplied non-AJAX single-board alert read link.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::notifications"
        }
      },
      "capability": "mark-notifications-read"
    },
    {
      "text": "The Product consults notification Read status",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "notification",
          "effect": "changes",
          "facts": [
            "Read status"
          ],
          "from": "Unread",
          "to": "Read"
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::notifications"
        }
      },
      "capability": "mark-notifications-read"
    },
    {
      "text": "The selected notification becomes Read and completion follows its stored destination.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "notification",
          "effect": "reads",
          "facts": [
            "Destination"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::notifications"
        }
      },
      "capability": "mark-notifications-read"
    },
    {
      "text": "The Product carries User through the completion destination into view shared message",
      "kind": "product",
      "actor": "user",
      "capability": "mark-notifications-read",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::notifications"
        }
      }
    },
    {
      "text": "The User selects an available mailbox copy.",
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
      "text": "The Product consults message copy Folder, New, Unread, Deleted",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "message-copy",
          "effect": "reads",
          "facts": [
            "Folder",
            "New",
            "Unread",
            "Deleted"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-message"
        }
      },
      "capability": "view-private-message"
    },
    {
      "text": "The content and filtered addressing are displayed; applicable read status, unread counters and associated notification status are updated.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "private-message",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Sender",
            "Sent at",
            "Formatting choices",
            "Edit information"
          ]
        },
        {
          "entity": "message-copy",
          "effect": "changes",
          "facts": [
            "Unread"
          ]
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Unread message count"
          ]
        },
        {
          "entity": "notification",
          "effect": "changes",
          "facts": [
            "Read status"
          ],
          "from": "Read",
          "to": "Read"
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-message"
        }
      },
      "capability": "view-private-message"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewtopic.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php#is_visible"
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

# Follow notification — user private message

## Trigger

Follow a board notification to its corresponding content.

## Outcome

A valid non-AJAX marking link marks the notification and carries its recipient to the topic or private-message view.
