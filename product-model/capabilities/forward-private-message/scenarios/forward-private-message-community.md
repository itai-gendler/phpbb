---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User forwards selected content to an accepted recipient with a valid form.",
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
      "text": "A new Sent message and copies are stored independently of the original; completion schedules the forwarded message. The supplied associated Uploaded attachment becomes Attached with this accepted parent. A notification is stored by the board method for the selected subscribed recipient.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "private-message",
          "effect": "creates",
          "facts": [
            "Subject",
            "Content",
            "Sender",
            "To recipients",
            "Blind-copy recipients",
            "Sent at",
            "Formatting choices",
            "Edit information",
            "Reply origin",
            "Attachments present"
          ],
          "to": "Sent"
        },
        {
          "entity": "message-copy",
          "effect": "creates",
          "facts": [
            "Owner",
            "Message",
            "Folder",
            "New",
            "Unread",
            "Deleted"
          ],
          "to": "Awaiting placement",
          "with": "private-message",
          "as": "recipient-copy"
        },
        {
          "entity": "account",
          "as": "recipient-account",
          "effect": "changes",
          "facts": [
            "New message count",
            "Unread message count"
          ]
        },
        {
          "entity": "account",
          "as": "sender-account",
          "effect": "changes",
          "facts": [
            "Last post at"
          ]
        },
        {
          "entity": "message-copy",
          "effect": "creates",
          "facts": [
            "Owner",
            "Message",
            "Folder",
            "New",
            "Unread",
            "Deleted"
          ],
          "to": "Available",
          "with": "private-message",
          "as": "sender-copy"
        },
        {
          "entity": "attachment",
          "effect": "changes",
          "facts": [
            "Binding"
          ],
          "from": "Uploaded",
          "to": "Attached"
        },
        {
          "entity": "notification",
          "effect": "creates",
          "to": "Unread",
          "facts": [
            "Recipient",
            "Event",
            "Origin",
            "Destination",
            "Created at",
            "Read status",
            "Display information"
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

# Forward private message — community

## Trigger

A subscribed recipient has the board method enabled. A selected uploaded file accompanies this accepted input. The sender forwards selected content to an accepted recipient with a valid form.


## Outcome

A new Sent message and copies are stored independently of the original; completion schedules the forwarded message.
