---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits a valid subject and content in a posting area.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "A topic and first post are stored Approved; contribution summaries are maintained, approved dispatch runs and completion points to the discussion. The supplied associated Uploaded attachment becomes Attached with this accepted parent. The board-method event is stored for a configured recipient; external delivery is not asserted.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "topic",
          "effect": "creates",
          "facts": [
            "Subject",
            "Author",
            "Forum",
            "Created at",
            "Visibility",
            "Posting status",
            "Topic type",
            "First post",
            "Last post",
            "Last contribution",
            "Approved count",
            "Unapproved count",
            "Deleted count",
            "Reported",
            "Attachments present",
            "Views"
          ],
          "to": "Approved"
        },
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
          "to": "Approved",
          "with": "topic"
        },
        {
          "entity": "forum",
          "effect": "changes",
          "facts": [
            "Topic counts",
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
        "web": {
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

# Post new topic — community

## Trigger

A selected uploaded file accompanies this accepted input. The contributor submits a valid subject and content in a posting forum.

## Outcome

A topic and first post are stored Approved; contribution summaries are maintained, approved dispatch runs and completion points to the discussion.
