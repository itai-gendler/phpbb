---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits supplied content, a supplied recipient and supplied form.",
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
      "text": "The sender chooses Reply to an existing disclosed message.",
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
      "text": "The selected reply origin is kept in the new Sent message; original content remains separate and new copies/dispatch follow ordinary sending. The supplied associated Uploaded attachment becomes Attached with this accepted parent. A notification is stored by the board method for the selected subscribed recipient.",
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

# Send private message — reply

## Trigger

A subscribed recipient has the board method enabled. A selected uploaded file accompanies this accepted input. The sender chooses Reply to an existing disclosed message.


## Outcome

The selected reply origin is kept in the new Sent message; original content remains separate and new copies/dispatch follow ordinary sending.
