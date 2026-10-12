---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The User forwards selected content to a supplied recipient with a supplied form.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-message"
        }
      },
      "capability": "forward-private-message"
    },
    {
      "text": "A new Sent message and copies are stored independently of the original; completion schedules the forwarded message. A notification is stored by the board method for the selected subscribed recipient.",
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
      },
      "capability": "forward-private-message"
    },
    {
      "text": "The Product carries User through the completion destination into view shared message",
      "kind": "product",
      "actor": "user",
      "capability": "forward-private-message",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-message"
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
      "text": "The sender views the new shared content through the available Outbox copy",
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
          ],
          "as": "sender-copy"
        },
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

# View submitted private message — user forward

## Trigger

A subscribed recipient has the board method enabled. Reach the message created by sending or forwarding.


## Outcome

The sender follows the submission completion destination and views the created message through the Outbox copy.
