---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Browser carried completion"
  },
  "steps": [
    {
      "text": "The User submits proposed edits to the selected contribution.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      },
      "capability": "edit-post"
    },
    {
      "text": "The post's content and editing information are saved; an edited first post also updates the topic subject and completion identifies the stored contribution.",
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
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      },
      "capability": "edit-post"
    },
    {
      "text": "The Product carries User through the completion destination into read discussion",
      "kind": "product",
      "actor": "user",
      "capability": "edit-post",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The User opens an approved discussion.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::topic"
        }
      },
      "capability": "read-topic"
    },
    {
      "text": "The Product consults topic Subject, Author, Approved count, Last contribution",
      "kind": "product",
      "actor": "user",
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
          "place": "forum-web::community::topic"
        }
      },
      "capability": "read-topic"
    },
    {
      "text": "The discussion presents its disclosed contributions and author information; reading increments the applicable view summary.",
      "kind": "product",
      "actor": "user",
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
          "place": "forum-web::community::topic"
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

# Publish and read contribution — user edit

## Trigger

Publish a contribution and reach its resulting discussion.

## Outcome

The same contributor follows the completion destination and reads the stored approved contribution.
