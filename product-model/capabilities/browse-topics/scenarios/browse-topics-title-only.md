---
{
  "kind": "primary",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens a posting area.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::forum"
        },
        "community": {
          "place": "forum-web::community::forum"
        }
      }
    },
    {
      "text": "The selected posting area offers discussion titles without ordinary discussion entry.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::forum"
        },
        "community": {
          "place": "forum-web::community::forum"
        }
      }
    },
    {
      "text": "Topic subjects and admitted list summaries are shown; the bodies are not supplied by this list.",
      "kind": "product",
      "actor": "user",
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
        "public": {
          "place": "forum-web::public::forum"
        },
        "community": {
          "place": "forum-web::community::forum"
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

# Browse topics — title only

## Trigger

The selected forum offers topic titles without ordinary discussion entry.

## Outcome

Topic subjects and admitted list summaries are shown; the bodies are not supplied by this list.
