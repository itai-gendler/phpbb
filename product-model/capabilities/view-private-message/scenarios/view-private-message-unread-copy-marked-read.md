---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User selects an available mailbox copy.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::private-message"
        }
      }
    },
    {
      "text": "The selected ordinary copy is Unread.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::private-message"
        }
      }
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
        "community": {
          "place": "forum-web::community::private-message"
        }
      }
    },
    {
      "text": "The content is shown, Unread becomes false and the owner's unread counter is decremented once; reading again does not decrement it again.",
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
          "from": "Unread",
          "to": "Read"
        }
      ],
      "contexts": {
        "community": {
          "place": "forum-web::community::private-message"
        }
      }
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
    }
  ]
}
---

# View private message — unread copy marked read

## Trigger

The selected ordinary copy is Unread and has its matching unread board notification.

## Outcome

The content is shown, Unread becomes false and the owner's unread counter is decremented once; reading again does not decrement it again.
