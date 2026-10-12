---
{
  "kind": "primary",
  "routes": {
    "public": "Public browser"
  },
  "steps": [
    {
      "text": "The Guest submits a supplied subject and content in a posting area.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::posting"
        }
      }
    },
    {
      "text": "The guest submission selects the pending-publication branch.",
      "kind": "condition",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::posting"
        }
      }
    },
    {
      "text": "The topic is stored Unapproved; pending summaries and the queue dispatch path are maintained and the moderation acknowledgement is shown. The supplied associated Uploaded attachment becomes Attached with this accepted parent. The board-method event is stored for a configured recipient; external delivery is not asserted. The configured queue recipient receives the queued-content event. Existing forum last-contribution information is retained; a queued reply also retains the topic’s previous last-post information.",
      "kind": "product",
      "actor": "guest",
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
          "to": "Unapproved"
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
          "to": "Unapproved",
          "with": "topic"
        },
        {
          "entity": "forum",
          "effect": "changes",
          "facts": [
            "Topic counts"
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
        "public": {
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

# Post new topic — guest queued

## Trigger

A selected uploaded file accompanies this accepted input. The guest submission selects the pending-publication branch.

## Outcome

The topic is stored Unapproved; pending summaries and the queue dispatch path are maintained and the moderation acknowledgement is shown.

## Summary boundary

Queued creation increments the pending counts. Existing forum last-contribution information is retained. A new topic retains its first/last reference to its initial queued post; a queued reply leaves the prior topic last-post summary unchanged.
