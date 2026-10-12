---
{
  "kind": "primary",
  "routes": {
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator confirms supplied delete-content/subforum choices.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::forum"
        }
      }
    },
    {
      "text": "The administrator confirms valid destinations for content/child movement.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::forum"
        }
      }
    },
    {
      "text": "Content/selected children are moved to the chosen surviving destination before the source container is removed; surviving destination summaries are synchronized.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Forum"
          ]
        },
        {
          "entity": "forum",
          "effect": "changes",
          "as": "moved-child",
          "facts": [
            "Parent"
          ]
        },
        {
          "entity": "forum",
          "effect": "removes",
          "as": "source-forum"
        },
        {
          "entity": "forum",
          "effect": "changes",
          "as": "destination-forum",
          "facts": [
            "Topic counts",
            "Last contribution"
          ]
        }
      ],
      "contexts": {
        "administration": {
          "place": "forum-web::administration::forum"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_forums.php"
    }
  ]
}
---

# Delete forum — move content

## Trigger

The administrator confirms valid destinations for content/child movement.

## Outcome

Content/selected children are moved to the chosen surviving destination before the source container is removed; surviving destination summaries are synchronized.
