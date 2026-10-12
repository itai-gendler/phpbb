---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The Guest submits a supplied subject and content in a posting area.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::posting"
        }
      },
      "capability": "post-new-topic"
    },
    {
      "text": "A topic and first post are stored Approved; contribution summaries are maintained, approved dispatch runs and completion points to the discussion.",
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
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::posting"
        }
      },
      "capability": "post-new-topic"
    },
    {
      "text": "The Product carries Guest through the completion destination into read discussion",
      "kind": "product",
      "actor": "guest",
      "capability": "post-new-topic",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::posting"
        }
      }
    },
    {
      "text": "The Guest opens an approved discussion.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::topic"
        }
      },
      "capability": "read-topic"
    },
    {
      "text": "The Product consults topic Subject, Author, Approved count, Last contribution",
      "kind": "product",
      "actor": "guest",
      "entities": [
        {
          "entity": "topic",
          "effect": "reads",
          "facts": [
            "Subject",
            "Author",
            "Approved count",
            "Last contribution"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::topic"
        }
      },
      "capability": "read-topic"
    },
    {
      "text": "The discussion presents its disclosed contributions and author information; reading increments the applicable view summary.",
      "kind": "product",
      "actor": "guest",
      "entities": [
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Author",
            "Guest name",
            "Posted at",
            "Edit information",
            "Visibility",
            "Formatting choices"
          ]
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Views"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::topic"
        }
      },
      "capability": "read-topic"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewtopic.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php#is_visible"
    }
  ]
}
---

# Publish and read contribution — guest topic

## Trigger

Publish a contribution and reach its resulting discussion.

## Outcome

The same contributor follows the completion destination and reads the stored approved contribution.
