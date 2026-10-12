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
      "text": "The ordinary author enters a pending discussion through configured own-pending visibility.",
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
      "text": "The admitted ordinary-author branch reaches replying; the explicit pending-discussion refusal does not occur on this branch. An accepted reply is stored through its publication branch. The supplied associated Uploaded attachment becomes Attached with this accepted parent. The board-method event is stored for a configured recipient; external delivery is not asserted. The configured queue recipient receives the queued-content event. The previous last-contribution summaries are retained.",
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
          "to": "Unapproved"
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Unapproved count",
            "Attachments present"
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

# Post reply — own pending topic

## Trigger

A selected uploaded file accompanies this accepted input. The ordinary author enters a pending topic through configured own-pending visibility.

## Outcome

The admitted ordinary-author branch reaches replying; the explicit pending-discussion refusal does not run on this branch. An accepted reply is stored through its publication branch.

## Summary boundary

Queued creation increments the pending counts. Existing forum last-contribution information is retained. A new topic retains its first/last reference to its initial queued post; a queued reply leaves the prior topic last-post summary unchanged.
