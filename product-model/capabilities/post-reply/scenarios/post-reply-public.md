---
{
  "kind": "primary",
  "routes": {
    "web": "Public browser"
  },
  "steps": [
    {
      "text": "The Guest submits a valid reply in an existing discussion.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::posting"
        }
      }
    },
    {
      "text": "An Approved reply is stored; summaries and approved dispatch are maintained and completion points to the stored reply. The supplied associated Uploaded attachment becomes Attached with this accepted parent. The board-method event is stored for a configured recipient; external delivery is not asserted.",
      "kind": "product",
      "actor": "guest",
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
        "web": {
          "place": "forum-web::public::posting"
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

# Post reply — public

## Trigger

A selected uploaded file accompanies this accepted input. The contributor submits a valid reply in an existing discussion.

## Outcome

An Approved reply is stored; summaries and approved dispatch are maintained and completion points to the stored reply.
