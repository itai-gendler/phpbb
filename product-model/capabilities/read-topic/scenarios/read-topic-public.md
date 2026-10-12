---
{
  "kind": "primary",
  "routes": {
    "web": "Public browser"
  },
  "steps": [
    {
      "text": "The Guest opens an approved discussion.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::topic"
        }
      }
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
      }
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
      }
    }
  ],
  "references": [
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

# Read topic — public

## Trigger

The visitor opens an approved discussion.

## Outcome

The discussion presents its disclosed contributions and author information; reading increments the applicable view summary.
