---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits proposed edits to the selected contribution.",
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
      "text": "The accepted edit changes the only Approved contribution in its discussion and selects reapproval.",
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
      "text": "The post becomes Reapproval required; applicable topic visibility and summaries are updated and the reapproval dispatch/result occurs. The supplied associated Uploaded attachment becomes Attached with this accepted parent. The forum summaries and the counted author’s account Post count are synchronized.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "post",
          "effect": "changes",
          "facts": [
            "Subject",
            "Content",
            "Formatting choices",
            "Edit information",
            "Attachments present",
            "Visibility"
          ],
          "from": "Approved",
          "to": "Reapproval required"
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Subject",
            "Attachments present",
            "Visibility",
            "Approved count",
            "Unapproved count",
            "First post",
            "Last post",
            "Last contribution"
          ],
          "from": "Approved",
          "to": "Reapproval required"
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
          "entity": "forum",
          "effect": "changes",
          "facts": [
            "Topic counts",
            "Last contribution"
          ]
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Post count"
          ]
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

# Edit post — reapproval

## Trigger

A selected uploaded file accompanies this accepted input. The contributor edits the only counted Approved post in its topic and submission selects reapproval.


## Outcome

The post becomes Reapproval required; applicable topic visibility and summaries are updated and the reapproval dispatch/result occurs.

## Edge cases

- When other approved contributions remain, editing a later post for reapproval adjusts counts and first/last summaries while the topic can remain Approved; its Subject is retained unless the edited contribution is the first.
