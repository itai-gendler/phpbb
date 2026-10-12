---
{
  "kind": "primary",
  "routes": {
    "web": "Public browser"
  },
  "steps": [
    {
      "text": "The Guest opens a posting area.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::forum"
        }
      }
    },
    {
      "text": "The list displays disclosed discussions with subjects, contribution summaries and paging.",
      "kind": "product",
      "actor": "guest",
      "entities": [
        {
          "entity": "forum",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Rules",
            "Topic counts",
            "Last contribution"
          ]
        },
        {
          "entity": "topic",
          "effect": "reads",
          "facts": [
            "Subject",
            "Author",
            "Created at",
            "Approved count",
            "Last contribution"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::forum"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/index.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewforum.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_display.php#display_forums"
    }
  ]
}
---

# Browse topics — public

## Trigger

The visitor opens a posting forum.

## Outcome

The list displays disclosed discussions with subjects, contribution summaries and paging.
