---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits a supplied reply in an existing discussion.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The contributor chooses Quote on a displayed contribution.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The editor includes the selected quotation and accepted submission stores a new reply without modifying the quoted contribution. The supplied associated Uploaded attachment becomes Attached with this accepted parent. The board-method event is stored for a configured recipient; external delivery is not asserted.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "post",
          "effect": "creates",
          "facts": [
            "Subject",
            "Content",
            "Author",
            "Guest name",
            "Posted at",
            "Author IP",
            "Formatting choices",
            "Edit information",
            "Edit lock",
            "Visibility",
            "Deletion information",
            "Count contribution",
            "Reported",
            "Attachments present"
          ],
          "to": "Approved"
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Approved count",
            "Last post",
            "Last contribution",
            "Attachments present"
          ]
        },
        {
          "entity": "forum",
          "effect": "changes",
          "facts": [
            "Last contribution"
          ]
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
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Post count",
            "Last post at"
          ]
        },
        {
          "entity": "notification",
          "effect": "creates",
          "facts": [
            "Recipient",
            "Event",
            "Origin",
            "Destination",
            "Created at",
            "Read status",
            "Display information"
          ],
          "to": "Unread"
        }
      ],
      "contexts": {
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/posting.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_posting.php#submit_post"
    }
  ]
}
---

# Post reply — quoted reply in community

## Trigger

A selected uploaded file accompanies this accepted input. The contributor chooses Quote on a displayed contribution.

## Outcome

The editor includes the selected quotation and accepted submission stores a new reply without modifying the quoted contribution.
