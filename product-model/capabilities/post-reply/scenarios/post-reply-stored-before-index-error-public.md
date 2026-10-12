---
{
  "kind": "edge",
  "routes": {
    "public": "Public browser"
  },
  "steps": [
    {
      "text": "The Guest submits a supplied reply in an existing discussion.",
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
      "text": "Accepted anonymous storage commits, then the configured search module cannot load.",
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
      "text": "The stored contribution and synchronized summaries remain, NO_SUCH_SEARCH_MODULE occurs after persistence. The supplied associated Uploaded attachment becomes Attached with this accepted parent.",
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

# Post reply — stored before index error in public

## Trigger

A selected uploaded file accompanies this accepted input. Accepted anonymous storage commits, then the configured search module cannot load.

## Outcome

The stored contribution and synchronized summaries remain, NO_SUCH_SEARCH_MODULE occurs after persistence.

## Edge cases

- Search-module failure precedes the later watch-choice/read-tracking and notification dispatch branches; those later branches are not reached for this failed run.
