---
{
  "kind": "primary",
  "routes": {
    "web": "Public browser"
  },
  "steps": [
    {
      "text": "The Guest submits a valid query and search options.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::search"
        }
      }
    },
    {
      "text": "The selected backend returns filtered topic or post results; no matches displays the empty result.",
      "kind": "product",
      "actor": "guest",
      "entities": [
        {
          "entity": "topic",
          "effect": "reads",
          "facts": [
            "Subject",
            "Author",
            "Created at",
            "Last contribution"
          ]
        },
        {
          "entity": "post",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Author",
            "Posted at"
          ]
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::search"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/search.php"
    }
  ]
}
---

# Search board — public

## Trigger

The visitor submits a valid query and search options.

## Outcome

The selected backend returns filtered topic or post results; no matches displays the empty result.
