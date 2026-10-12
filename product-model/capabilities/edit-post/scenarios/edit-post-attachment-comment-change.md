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
      "text": "The contributor accepts a comment change on an associated submitted uploaded file while editing.",
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
      "text": "The changed Comment persists with accepted parent editing, not as an independent attachment-comment operation. The supplied associated Uploaded attachment becomes Attached with this accepted parent.",
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
            "Attachments present"
          ]
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Subject",
            "Attachments present"
          ]
        },
        {
          "entity": "attachment",
          "effect": "changes",
          "facts": [
            "Comment",
            "Binding"
          ],
          "from": "Uploaded",
          "to": "Attached"
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

# Edit post — attachment comment change

## Trigger

A selected uploaded file accompanies this accepted input. The contributor accepts a comment change on an associated submitted attachment while editing.

## Outcome

The changed Comment persists with accepted parent editing, not as an independent attachment-comment operation.
