---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits a valid query and search options.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::search"
        }
      }
    },
    {
      "text": "The selected backend returns filtered topic or post results; no matches displays the empty result.",
      "kind": "product",
      "actor": "user",
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
          "place": "forum-web::community::search"
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

# Search board — community

## Trigger

The visitor submits a valid query and search options.

## Outcome

The selected backend returns filtered topic or post results; no matches displays the empty result.
