---
{
  "kind": "edge",
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
      "text": "Accepted storage commits, consumes a loaded draft, then the configured search module cannot load.",
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
      "text": "The stored contribution and synchronized summaries remain, the loaded owner draft is removed, and NO_SUCH_SEARCH_MODULE occurs after persistence. The supplied associated Uploaded attachment becomes Attached with this accepted parent.",
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
          "entity": "forum-draft",
          "effect": "removes",
          "from": "Saved"
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

# Post reply — stored before index error in community

## Trigger

A selected uploaded file accompanies this accepted input. Accepted storage commits, consumes a loaded draft, then the configured search module cannot load.

## Outcome

The stored contribution and synchronized summaries remain, the loaded owner draft is removed, and NO_SUCH_SEARCH_MODULE occurs after persistence.

## Edge cases

- Search-module failure precedes the later watch-choice/read-tracking and notification dispatch branches; those later branches are not reached for this failed run.
