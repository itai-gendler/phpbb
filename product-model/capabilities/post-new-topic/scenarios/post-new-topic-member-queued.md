---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits a supplied subject and content in a posting area.",
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
      "text": "The signed-in submission selects the pending-publication branch.",
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
      "text": "The topic is stored Unapproved, pending summaries and queue dispatch are maintained, and completion follows the visible/missing pending destination. The supplied associated Uploaded attachment becomes Attached with this accepted parent. The board-method event is stored for a configured recipient; external delivery is not asserted. The configured queue recipient receives the queued-content event. Existing forum last-contribution information is retained; a queued reply also retains the topic’s previous last-post information.",
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
          "entity": "account",
          "effect": "changes",
          "facts": [
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

# Post new topic — member queued

## Trigger

A selected uploaded file accompanies this accepted input. The signed-in submission selects the pending-publication branch.

## Outcome

The topic is stored Unapproved, pending summaries and queue dispatch are maintained, and completion follows the visible/missing pending destination.

## Summary boundary

Queued creation increments the pending counts. Existing forum last-contribution information is retained. A new topic retains its first/last reference to its initial queued post; a queued reply leaves the prior topic last-post summary unchanged.
