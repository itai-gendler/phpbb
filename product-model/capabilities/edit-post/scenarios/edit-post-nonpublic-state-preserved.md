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
      "text": "The selected contribution is nonpublic and the accepted edit takes the preserve-state branch.",
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
      "text": "Edited content is stored while the prior Unapproved or Reapproval required classification is preserved as implemented. The supplied associated Uploaded attachment becomes Attached with this accepted parent.",
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

# Edit post — nonpublic state preserved

## Trigger

A selected uploaded file accompanies this accepted input. The selected contribution is nonpublic and the accepted edit takes the preserve-state branch.

## Outcome

Edited content is stored while the prior Unapproved or Reapproval required classification is preserved as implemented.
