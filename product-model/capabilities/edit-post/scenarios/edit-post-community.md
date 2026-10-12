---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits accepted edits to the selected contribution.",
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
      "text": "The post's content and editing information are saved; an edited first post also updates the topic subject and completion identifies the stored contribution. The supplied associated Uploaded attachment becomes Attached with this accepted parent.",
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

# Edit post — community

## Trigger

A selected uploaded file accompanies this accepted input. The contributor submits accepted edits to the selected post.

## Outcome

The post's content and editing information are saved; an edited first post also updates the topic subject and completion identifies the stored contribution.
