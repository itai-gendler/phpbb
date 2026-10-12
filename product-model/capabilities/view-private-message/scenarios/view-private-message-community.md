---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User selects an Available mailbox copy whose Unread flag is already false",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
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
        "web": {
          "place": "forum-web::community::private-message"
        }
      }
    },
    {
      "text": "The Product displays the private message content and the message copy status without decrementing an unread counter again",
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

# View private message — community

## Trigger

The User selects an Available copy that is already read.

## Outcome

The disclosed message content and filtered addressing are displayed. The already-read copy does not decrement the account’s unread counter again.
